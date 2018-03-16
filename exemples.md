**Navigation**
* [Accueil](index.html)
* [Présentation d'Ethereum](ethereum.html)
* [Qu'est-ce qu'un smart-contract ?](smartcontracts.html)
* [Les applications de ces contrats](applications.html)
* [**Exemples de code Solidity**](exemples.html)
* [Sécurité des smart-contracts](securite.html)
* [Le futur de la technologie](futur.html)
* [Bibliographie](bibliographie.html)

___
# Exemples de code Solidity

## Repository des exemples
Pour avoir une vue plus complète des différents contrats que j'ai écris et testé, rendez vous sur la page de mon projet GitHub : [https://github.com/Leo-Besancon/exercices-b2expand](https://github.com/Leo-Besancon/exercices-b2expand) !

Les dossiers de chaque contrats contiennent un fichier README.md dans lequel je décris les différentes actions réalisées, les contrats (fichiers *.sol) et les interfaces ABI décrivants les signatures des
fonctions afin d'intéragir avec eux depuis un site comme [MyEtherWallet](https://myetherwallet.com).

Ce projet m'a permis de découvrir la syntaxe de Solidity ainsi que de mieux comprendre les enjeux de sécurité derrière les smart-contracts.

## Détails sur les contrats

J'ai ainsi écrit 5 contrats que j'ai publié sur le Test-net Ropsten. Un Test-net permet de déployer et tester des contrats sans avoir a payer des transactions,
et pour éviter d'avoir un contrat vulnérable en cours de développement qui puisse être utilisé avec de l'argent réel.

### Premier contrat : Déploiement d'un Token ERC20

Un Token est une crypto-monnaie qui repose sur un smart-contract. Ce contrat stocke les balances associées aux différentes adresses qui ont intéragient avec le contrat, dans la map : `mapping(address => uint256) balances;`

ERC20 est un standard de token : il définit l'ensemble de fonctions qu'un token doit implémenter pour facilité l'intégration dans l'écosystème Ethereum.
 
 La fonction intéressante du contrat est celle qui gère les transferts de token d'un compte à un autre :
 
```javascript
function transfer(address _to, uint _value) public returns (bool success) {
    if (balances[msg.sender] >= _value 
        && _value > 0
        && balances[_to] + _value > balances[_to] // Protects from overflow
		) {
        balances[msg.sender] -= _value;
        balances[_to] += _value;
        Transfer(msg.sender, _to, _value); // Event must be sent
        return true;
    } else {
        return false;
    }
}
```

Ici, il est important de vérifier que les arguments donnés à la fonction sont valides et qu'il n'y a pas d'effet de bord.

### Deuxième contrat : Vendre ce token par crowdfunding (_Initial Coin Offering_, ou ICO)

Le principe de ce contrat est simple : les investisseurs doivent pouvoir envoyer des Ether au contrat, et recevoir en échange des tokens.

Un des paramètres du contrat est un seuil de financement : si ce seuil n'est pas atteint avant la fin de la crowdsale, il faut que les investisseurs puissent retirer leurs Ether grâce à la fonction `withdrawIfFailed()` :

```javascript
function withdrawIfFailed() public returns (bool success){
	if (!receipts[msg.sender].withdrew
		&& icoEnded()
		&& !goalReached()
		) {
			uint _value = receipts[msg.sender].EthSent;
			receipts[msg.sender].withdrew = true;
			if (!msg.sender.send(_value)) revert();
		return true;
	} else {
		return false;
	}
}
```

Dans cette fonction, on récupère le reçu associé à l'investissement d'une personne dans l'ICO, on regarde sa valeur, puis on rembourse en fonction de cette valeur (en vérifiant bien qu'il n'a pas déjà retirer son argent !).

### Troisième contrat : Investir dans cette ICO via un smart-contract tiers

Ce contrat m'a permis de comprendre comment fonctionne les appels de fonctions entre les différents contrats. À partir de l'interface d'un contrat et de son adresse sur la blockchain,
nous pouvons en effet directement appeler les fonctions de ce contrat depuis un autre.

```javascript
function Invest() public payable {
	require(msg.value > 0);
	ico.DelegateTokenTo.value(msg.value)(msg.sender);
}
```

### Quatrième contrat : Implémenter des payment channels

Je n'ai pas réussi a faire fonctionner ce code, mais le principe était de pouvoir implémenter des payments channels. Ils permettent en effet de pouvoir réaliser des transactions _hors-chaîne_,
c'est-à-dire sans diffuser la transaction aux mineurs. La signature de messages permet en effet en principe de vérifier après coup une transaction.

### Cinquième contrat : Introduire une vulnérabilité dans le contrat d'ICO

Ici, le but est de recréer la faille (appelée _Re-entrancy attack_) du DAO qui à permis à un hacker de voler un grand nombre d'Ether en 2016 (plus d'informations page suivante).
Depuis ce hack, Solidity a été patché pour éviter que d'autres contrats soient vulnérables, donc la vulnérabilité que j'ai exploité ne pourrait pas être introduite par erreur.

Lorsqu'on envoie des Ether à un contrat, une fonction spéciale est appelée, la fonction de _fallback_ du contrat. L'attaque utilise cette fonction pour voler les fonds d'un autre contrat.

La vulnérabilité du contrat de crowdfunding attaqué provient de la fonction `withdrawIfFailed` suivante :

```javascript
function withdrawIfFailed() public returns (bool success){
	if (!receipts[msg.sender].withdrew
		&& icoEnded()
		&& !goalReached()
		) {
			uint _value = receipts[msg.sender].EthSent;
			if (!msg.sender.call.value(_value)()) {revert();}  // We use call instead of send to forward the remaining gas.
			receipts[msg.sender].withdrew = true;	// We set withdrew to true after sending the funds, to allow the re-entrancy attack
		return true;
	} else {
		return false;
	}
}
```

Ici, lorsque quelqu'un retire son argent, le booléen `withdrew` est bien mis à jour, mais après que notre contrat lui envoie l'argent.

Ainsi, si le contrat de l'attaquant retire son argent, on lui envoie des Ether ce qui appelle la fonction de fallback du contrat :

```javascript
function () public payable {
	if (ico.balance > msg.value)	// If there isn't enough Ether in the ICO contract, don't callback, or it will give an error and revert
	{
		ico.call(bytes4(keccak256("withdrawIfFailed()")));		// Use .call() so it doesn't revert if it throws
	}
}
```

On voit que l'appel de cette fonction redemande de retirer de l'argent au contrat initial. Comme le booléen `withdrew` n'a pas encore été mis à jour à ce moment,
l'appel réussi, et l'attaquant peut siphonné la totalité des fonds du contrat.

À lire ensuite : [**Sécurité des smart-contracts ->**](securite.html)

___
[Me contacter](mailto://leo.besancon@ecl14.ec-lyon.fr)

Suivez mon flux Twitter : [@ecl_lb](https://twitter.com/ecl_lb) !
