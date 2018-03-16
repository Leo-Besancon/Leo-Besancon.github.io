**Navigation**
* [Accueil](index.html)
* [Présentation d'Ethereum](ethereum.html)
* [Qu'est-ce qu'un smart-contract ?](smartcontracts.html)
* [Les applications de ces contrats](applications.html)
* [Exemples de code Solidity](exemples.html)
* [**Sécurité des smart-contracts**](securite.html)
* [Le futur de la technologie](futur.html)
* [Bibliographie](bibliographie.html)

___
# Sécurité des smart-contracts

Certains contrats doivent gérer de très grosses sommes d'argent. Il est donc normal de se demander à quel point les
fonds utilisés par ces contrats sont sécurisés contre des pertes ou vols. Nous devons séparer la notion de sécurité
entre le protocole et les contrats eux-mêmes, de la même façon qu'un site internet peut être vulnérable à une faille
à cause de vulnérabilités des technologies de chiffrement qu'il utilise ou bien de son propre code.

## Sécurité de la blockchain

La blockchain est une technologie récente, mais elle fait également parti des plus étudiées d'un point de vue de la sécurisé.
En effet, depuis la création de Bitcoin, de nombreux chercheurs ont cherché des vulnérabilités dans le principe ou dans le code.

L'algorithme de consensus utilisé par Ethereum actuellement, le _Proof of Work_, fait cependant quelques hypothèses pour supposer
la sécurité qui pourraient ne pas être remplis

### Attaque par 51%

Une attaque par 51% suppose qu'un des mineurs du réseau (ou un groupe de mineurs qui pratiquent la collusion) peut manipuler les transactions réalisées s'il possède plus de 51%
de la puissance de calcul (ou _hashrate_) de tous les mineurs. Ce genre d'attaque est cependant difficile à mettre en oeuvre en pratique puisqu'il est toujours possible
de forker la blockchain afin de la restaurer à un point avant le hack et annuler les transactions malveillantes réalisées.

Cependant, c'est une réelle possibilité puisqu'un petit nombre de mineurs (pour Bitcoin surtout, mais également pour Ethereum) possède une part importante du _hashrate_.

## Sécurité des smart-contracts

### Hack du DAO : _Re-entrancy attack_

Le principe de ce hack est utilisé dans le dernier contrat d'exemple décrit précédemment. En 2016, TheDAO, vulnérable à cette faille, a pu être hacké et un attaquant à volé 
[3.6 millions d'Ether](https://www.coindesk.com/dao-attacked-code-issue-leads-60-million-ether-theft/), valués à l'époque à 60 millions de dollars. Il en a résulté un fork de la
blockchain Ethereum.

### Hack de EtherDelta : 

Ce hack vise alors un point faible des applications décentralisées actuelles : le front-end. Tout le monde peut interagir purement
avec le contrat, mais une interface graphique nécessaire pour améliorer l'expérience utilisateur.

Les attaquants ont en effet utilisé le principe du [DNS Hijacking](https://www.ccn.com/cryptocurrency-exchange-etherdelta-hacked-in-dns-hijacking-scheme) pour s'approprier le nom
de domaine du site permettant d'interagir avec le contrat, puis en créant une copie du site afin de _phisher_ les clés privées des utilisateurs.

Ainsi, les concepts de sécurité web classiques s'appliquent également pour les applications décentralisées, à moins de changer la façon dont le front-end est
délivré (si par exemple les pages sont sécurisées sur un stockage décentralisé comme IPFS ou Swarm).

### Génération de nombres aléatoires

[Des études](https://blog.positive.com/predicting-random-numbers-in-ethereum-smart-contracts-e5358c6b8620) ont montré que de nombreux contrats sont vulnérables à cause de la façon dont ils génèrent des nombres aléatoires. Ces RNG sont nécessaires au fonctionnement
de nombreux contrats (comme les jeux d'argents basés sur la chance), et peuvent être manipulés s'ils ne sont pas créés correctement.

En effet, certains développeurs utilisent par exemple la parité du hash du block en cours afin de déterminer l'issue d'un contrat. Le problème étant que les mineurs peuvent choisir
quelles transactions sont incluses dans le block qu'ils créés, et il leur suffit donc de choisir d'inclure la transaction dans un block possédant un hash particulier plutôt qu'un autre.

À lire ensuite : [**Le futur de la technologie ->**](futur.html)

___
[Me contacter](mailto://leo.besancon@ecl14.ec-lyon.fr)

Suivez mon flux Twitter : [@ecl_lb](https://twitter.com/ecl_lb) !
