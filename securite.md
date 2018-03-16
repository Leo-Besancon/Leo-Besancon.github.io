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

La blockchain est une technologie récente, mais elle fait également parti des plus étudiée d'un point de vu de la sécurisé.
En effet, depuis la création de Bitcoin, de nombreux chercheurs ont cherché des vulnérabilités dans le principe ou dans le code.
[REFERENCE NECESSAIRE !]()

L'algorithme de consensus utilisé par Ethereum actuellement, le _Proof of Work_, fait cependant quelques hypothèses pour supposer
la sécurité qui pourraient ne pas être remplits

### Attaque par 51%


## Sécurité des smart-contracts

### Hack du DAO : _Re-entrancy attack_

Pour comprendre ce hack, il faut comprendre la gestion des payements par les contrats. Lorsque que quelqu'un (une personne ou un autre contrat) envoie des Ether
à l'adresse d'un contrat, une fonction spéciale, appelée fonction de fallback "()", est appelée.

Ainsi, dans le code suivant, le contrat appelera la fonction de fallback du contrat qui a appelé la fonction "" : 


Mais dans sa fonction de fallback, le contrat malveillant appelle de nouveau la fonction "". Cela créé donc une boucle de paiement, et
la balance du contrat ciblé est vidée.


### Hack de EtherDelta : 

Ce hack vise alors un point faible des applications décentralisées actuelles : le front-end. Tout le monde peut interagir purement
avec le contrat, mais une interface graphique nécessaire pour améliorer l'expérience utilisateur.

Ainsi, les concepts de sécurité web classiques s'appliquent également pour les applications décentralisées, à moins de changer la façon dont le front-end est
délivré (si par exemple les pages sont sécurisées sur un stockage décentralisé comme IPFS ou Swarm).


### Génération de nombre aléatoires

Des études ont montrés que de nombreux contrats sont vulnérables à cause de la façon dont ils génèrent des nombres aléatoires. Ces RNG sont nécessaires au fonctionnement
de nombreux contrats (comme les jeux d'argents basés sur la chance), et peuvent être manipulés s'ils ne sont pas créés correctement.






À lire ensuite : [**Le futur de la technologie**](futur.html)

___
[Me contacter](mailto://leo.besancon@ecl14.ec-lyon.fr)

Suivez mon flux Twitter : [@ecl_lb](https://twitter.com/ecl_lb) !
