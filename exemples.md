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

Ce projet m'a permi de découvrir la syntaxe de Solidity ainsi que de mieux comprendre les enjeux de sécurité derrière les smart-contracts.

## Détails sur les contrats

J'ai ainsi écrit 5 contrats que j'ai publié sur le Test-net Ropsten. Un Test-net permet de déployer et tester des contrats sans avoir a payer des transactions,
et pour éviter d'avoir un contrat vulnérable en cours de développement qui puisse être utilisé avec de l'argent réel.

### Premier contrat : Déploiement d'un Token ERC20

Un Token est une crypto-monnaie qui repose sur un smart-contract. Ce contrat stocke les balances associées aux différentes adresses qui ont intéragient avec le contrat.

ERC20 est un standard de token : il définit l'ensemble de fonctions qu'un token doit implémenter pour facilité l'intégration dans l'écosystème Ethereum.


### Deuxième contrat : Vendre ce token par crowdfunding (_Initial Coin Offering_, ou ICO)

Le principe de ce contrat est simple : les investisseurs doivent pouvoir envoyer des Ether au contrat, et recevoir en échange des tokens.



Un des paramètres du contrat est un seuil de financement : si ce seuil n'est pas atteint avant la fin de la crowdsale, il faut que les investisseurs puissent retirer leurs Ether.



### Troisième contrat : Investir dans cette ICO via un smart-contract tiers

Ce contrat m'a permis de comprendre comment fonctionne les appels de fonctions entre les différents contrats.



### Quatrième contrat : Implémenter des payment channels

Je n'ai pas réussi a faire fonctionner ce code, mais le principe était de pouvoir implémenter des payments channels. Ils permettent en effet de pouvoir réaliser des transactions _hors-chaîne_,
c'est-à-dire sans diffuser la transaction aux mineurs. La signature de messages permet en effet en principe de vérifier après coup une transaction.



### Cinquième contrat : Introduire une vulnérabilité dans le contrat d'ICO

Ici, le but est de recréer la faille (appelée _Re-entrancy attack_) du DAO qui à permis à un hacker de voler un grand nombre d'Ether en 2016 (plus d'information page suivante).
Depuis ce hack, Solidity a été patché pour éviter que d'autres contrats soient vulnérables, donc la vulnérabilité que j'ai exploité ne pourrait pas être introduite par erreur.

À lire ensuite : [**Sécurité des smart-contracts**](securite.html)

___
[Me contacter](mailto://leo.besancon@ecl14.ec-lyon.fr)

Suivez mon flux Twitter : [@ecl_lb](https://twitter.com/ecl_lb) !
