**Navigation**
* [Accueil](index.html)
* [Présentation d'Ethereum](ethereum.html)
* [**Qu'est-ce qu'un smart-contract ?**](smartcontracts.html)
* [Les applications de ces contrats](applications.html)
* [Exemples de code Solidity](exemples.html)
* [Sécurité des smart-contracts](securite.html)
* [Le futur de la technologie](futur.html)
* [Bibliographie](bibliographie.html)

___
# Qu'est-ce qu'un smart-contract ?

## Principe générale

Un smart-contract est un programme qui réside sur la blockchain. Les utilisateurs d'un contrat peuvent appeler ses fonctions de la 
même manière qu'ils réalisent des transactions classiques, avec des clients tels que [MetaMask](https://metamask.io/) (fonctionnant directement depuis le navigateur)
de l'utilisateur et utilisant un noeud tiers) ou [Mist](https://github.com/ethereum/mist/releases) (un programme tiers qui créé un noeud sur l'ordinateur de l'utilisateur).

Une fois la transaction diffusée, les mineurs vont exécuter le code du contrat et mettre à jour l'état des variables stockées sur la blockchain.
Les traces d'exécutions sont également stockées.

## Fonctionnement technique de l'_Ethereum Virtual Machine_ (EVM)

### Gas
Afin d'éviter les problèmes de spams de transactions (un acteur malveillant pourrait inonder le réseau de transactions inutiles
qui monopoliseraient les ressources de calculs des mineurs), un coût est associé à chaque transaction. Concrêtement, chaque transaction
se voit attribuer un nombre de _gas_ selon la complexité des calculs associés, et l'utilisateur doit payer des frais proportionnels aunombre de
_gas_ consommés lors de l'exécution de la transaction. Ce principe permet de rendre une inondation de transaction trop chère pour
être efficace.

### Langage et compilation

Plusieurs langages sont mis à disposition aux développeurs pour écrire des smart-contracts. Le plus utilisé actuellement est
[Solidity](https://github.com/ethereum/solidity), mais il y a aussi [Viper](https://github.com/ethereum/vyper) ([Serpent](https://github.com/ethereum/serpent) étant _deprecated_).

Viper à pour but de réduire le nombre de fonctionnalités par rapport à Solidity afin de simplifier les audits de sécurités du code
des smart-contracts.

Une fois écris, les smart-contracts sont compilés en Bytecode (l'assembleur de la blockchain), c'est-à-dire traduits en une série
d'instructions de base (appelés _opcodes_) décrites dans le [Papier Jaune d'Ethereum](https://github.com/ethereum/yellowpaper).

## Environnement de développement

Pour développer des smart-contracts, la suite d'outils la plus utilisée est [Truffle](http://truffleframework.com/).
Cependant, un IDE en ligne est également disponible pour prototyper rapidement des smart-contracts : [Remix](https://remix.ethereum.org)

Peu d'outils avancés d'aide au développement existent à l'heure actuelle. Cependant, nous pouvons noter l'existance d'un décompileur, [Porosity](https://github.com/comaeio/porosity)
pour transformer du bytecode en Solidity, ce qui est utile pour débuguer un contrat.

Truffle intègre aussi la possibilité d'exécuter des tests simulants des intéractions avec le contrat, écrits en Javascript.

## Pourquoi vouloir utiliser une blockchain ?

La technologie blockchain est très récente (création de Bitcoin en 2009), et de nombreuses personnes restent sceptiques sur son utilité.
En effet, beaucoup de _hype_ est apporté par les cours des cryptomonnaies et les capacités de la technologie sont plutôt mal connues,
et ceux même parmis les acteurs du domaine. Également, certaines personnes pensent que des systèmes distribués classiques pourraient
suffire pour de nombreux projets se basants sur la blockchain.

Cependant, les blockchains ont tout de même des avantages très intéressants :
* Tranparence : toutes les transactions sont visibles et vérifiables par chacun.
* Fiabilité : Une application décentralisée ne dépend pas d'un serveur central pour fonctionné, ainsi la probabilité de pannes de l'application est négligeable par design,
sans avoir à investir massivement dans une infrastructure complexe.
* Pas besoin de confiance en un tiers : si le code est de confiance, alors intéragir avec le smart-contract est sûr. Le fonctionnement de certaines plateforme de jeux d'argents en ligne,
par exemple, ont volé leurs clients en manipulant leur algorithme propriétaire. [TODO : SOURCES !]()
* Immuabilité : Personne ne peut modifier les événements passés (le coût de modification d'une transaction est en exponentiel du temps passé).
* Gestion des payements intégrée au protocole : Pas besoin de passé par un tiers tel Paypal qui peut bannir arbitrairement des comptes et applique des frais importants.


À lire ensuite : [**Les applications de ces contrats**](applications.html)

___
[Me contacter](mailto://leo.besancon@ecl14.ec-lyon.fr)

Suivez mon flux Twitter : [@ecl_lb](https://twitter.com/ecl_lb) !
