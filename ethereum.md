**Navigation**
* [Accueil](index.html)
* [**Présentation d'Ethereum**](ethereum.html)
* [Qu'est-ce qu'un smart-contract ?](smartcontracts.html)
* [Les applications de ces contrats](applications.html)
* [Exemples de code Solidity](exemples.html)
* [Sécurité des smart-contracts](securite.html)
* [Le futur de la technologie](futur.html)
* [Bibliographie](bibliographie.html)

___
# Présentation d'Ethereum

Ethereum est une blockchain publique. Cela signifie que n'importe qui peut intéragir avec, créer un noeud ou encore miner pour sécuriser le réseau.

## Qu'est-ce qu'une blockchain ?

Une blockchain est, au plus haut niveau, un livre de compte publique et décentralisé dont les seules modifications possibles sont des ajouts.
Ainsi, tout le monde peut diffuser une transaction à l'ensemble du réseau, et, si cette transaction est inclus dans un block de transaction, l'ensemble
des clients mettront à jour leur copie de la blockchain.

Le problème est alors de pouvoir décider quelles transactions sont intégrés dans le prochain block. En effet, nous pourrions imaginer que quelqu'un créé un conflit
en diffusant deux transactions contradictoires. Pour éviter cela, les blockchain ont besoin d'un algorithme de consensus. Le plus utilisé est le _Proof of Work_,
dans lequel des acteurs, appelés mineurs, doivent calculer des hashs par bruteforce afin d'en trouver un qui satisfait une condition spécifique.

Une autre forme de consensus est la _Proof of Stake_, dans laquel les personnes validant les blocks attestent de leur bonne fois en mettant une certaine somme d'argent
en collatérale : s'ils sont identifiés comme malveillants, ils perdent de l'argent.

De nombreuses ressources externes détaillent le fonctionnement d'une blockchain, mais cela sort du contexte de ma veille. Une bonne explication des concepts de base 
et des besoins de la cryptographie pour faire fonctionner un tel système peut se trouver sur la chaîne Youtube [3Blue1Brown](https://www.youtube.com/channel/UCYO_jab_esuFRV4b17AJtAw) :
[Ever wonder how Bitcoin (and other cryptocurrencies) actually work?](https://www.youtube.com/watch?v=bBC-nXj3Ng4) :
[![Ever wonder how Bitcoin (and other cryptocurrencies) actually work?](https://img.youtube.com/vi/bBC-nXj3Ng4/0.jpg)](https://www.youtube.com/watch?v=bBC-nXj3Ng4)

Vous pouvez également lire les synthèses des autres personnes ayant réalisé leur veille sur la blockchain.

## Spécificités d'Ethereum

Ethereum est une blockchain créée par Vitalik Buterin, un ancien développeur de Bitcoin, en 2014. Elle utilise la _Proof of Work_, mais devrait passer prochainement à la _Proof of Stake_.

En plus de pouvoir transférer sa cryptomonnaie, l'Ether, comme le permet Bitcoin, Ethereum intègre à son protocole la gestion de smart-contracts, qui sont des programmes exécutés par les mineurs de façon décentralisée.
Vous trouverez plus de détails sur les smart-contracts dans la page associée.

Ethereum est devenu rapidement une des blockchain les plus suivies et utilisée.

Quelques métriques intéressantes sur la plateforme :
* Deuxième projet blockchain par capitalisation du marché des cryptomonnaies
* Truffle : 360 000 téléchargements
* Une estimation de 100 000 développeurs sur la plateforme

À lire ensuite : [**Qu'est-ce qu'un smart-contract ?**](smartcontracts.html)

___
[Me contacter](mailto://leo.besancon@ecl14.ec-lyon.fr)

Suivez mon flux Twitter : [@ecl_lb](https://twitter.com/ecl_lb) !
