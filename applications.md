**Navigation**
* [Accueil](index.html)
* [Présentation d'Ethereum](ethereum.html)
* [Qu'est-ce qu'un smart-contract ?](smartcontracts.html)
* [**Les applications de ces contrats**](applications.html)
* [Exemples de code Solidity](exemples.html)
* [Sécurité des smart-contracts](securite.html)
* [Le futur de la technologie](futur.html)
* [Bibliographie](bibliographie.html)

___
# Les applications de ces contrats

## Plateformes de jeux d'argents

Les jeux d'argent sont une des cibles principales des smart-contracts. En effet, des casinos en ligne ont déjà été accusés de triche, et le code de leurs plateformes
étant fermé, il peut être difficile de leur faire confiance. Avec les smart-contracts, l'utilisateur peut lire directement le code et n'a pas besoin 
en théorie de faire confiance aux développeurs. De plus, de nombreux jeux d'argent sont relativement simples à programmer.

### [Decent.bet](https://decent.bet) et leur [Papier Blanc](https://decent.bet/whitepaper)

Cette application permet de parier sur les résultats sportifs. Elle utilise le principe des Oracles pour récupérer les flux de résultats du monde extérieur.
Les Oracles permettent aux contrats d'interagir avec le monde extérieur. Des redondances des flux sont programmées afin de minimiser les effets de la corruption
d'un flux spécifique.

### [FunFair](https://funfair.io/) et leurs Papiers Blancs [Commercial](https://funfair.io/wp-content/uploads/FunFair-Commercial-White-Paper.pdf) et [Technique](https://funfair.io/wp-content/uploads/FunFair-Technical-White-Paper.pdf)

FunFair souhaite devenir une des plus grosses plateformes de casino décentralisé, permettant aux développeurs d'ajouter leurs jeux à la plateforme.

## Création de tokens

### Levées de fonds par ICO

De nombreuses startups utilisent la création de tokens afin de réaliser des levées de fonds auprès du grand public. En 2017, 500 startups ont levé
un total de pas moins de [6.8 milliards de dollars](https://www.bloomberg.com/news/articles/2018-01-21/to-ico-or-not-to-ico-that-is-the-question-for-today-s-startups)
, dépassant largement [les financements par Venture Capital](https://www.cnbc.com/2017/08/09/initial-coin-offerings-surpass-early-stage-venture-capital-funding.html)

![Financements par ICO par trimestre](icos.png)
Source : [Smith et Crown](https://www.smithandcrown.com/icos/) et [https://www.bloomberg.com/news/articles/2018-01-21/to-ico-or-not-to-ico-that-is-the-question-for-today-s-startups](https://www.bloomberg.com/news/articles/2018-01-21/to-ico-or-not-to-ico-that-is-the-question-for-today-s-startups)

### Création de stablecoins (Dai, par [MakerDAO](https://makerdao.com/) et le [Papier Blanc](https://makerdao.com/whitepaper/DaiDec17WP.pdf))

Les cryptomonnaies sont très volatiles, ce qui peut poser un problème lorsque l'on souhaite les dépenser. Dai est un token qui, par un mécanisme complexe
géré par MakerDAO, reste stable par rapport au dollar.

L'intérêt est que les smart-contracts d'Ethereum peuvent gérer facilement le paiement par Dai à la place de l'Ether, puisque Dai est un token ERC20 sur Ethereum.

## Automatisation de processus

### [Fizzy](https://fizzy.axa/) et leur [vidéo de présentation](https://www.youtube.com/watch?v=C4RxizgkVxQ)

Fizzy, développé par Axa, est une assurance automatisée pour indemniser les retards d'avion. Les contrats consultent (par des Oracles) les bases de 
données d'horaires des vols et détermine automatiquement, quelques minutes après l'atterrissage, si le client doit être indemnisé ou non.

## Partage de ressources

### [Storj](https://storj.io/) et leur [Papier Blanc](https://storj.io/storj.pdf)

Storj est un Cloud décentralisé : vos fichiers sont découpés en _shards_, chiffrés, puis répartis sur différents noeuds du réseau souhaitant louer leur espace
de stockage disponible, avec redondance.

### [iExec](https://iex.ec) et leur [Papier Blanc](https://iex.ec/app/uploads/2017/04/iExec-WPv2.0-English.pdf) 

iExec fonctionne sur le même principe, mais en remplaçant l'espace de stockage par de la puissance de calcul. Cela permet aux utilisateurs de louer sur demande
des ressources CPU et GPU afin de réaliser du calcul distribué.

## Création de _Decentralized Autonomous Organizations_ (DAO)

Enfin, une des applications les plus ambitieuses des smart-contracts est la création de _Decentralized Autonomous Organizations_. Ces organisations agissent comme
des entreprises, mais sont dirigées par un programme et non par une structure humaine. Les investisseurs peuvent cependant modifier les différents paramètres
du programme par le vote, comme c'est le cas pour MakerDAO.

## ... Et de nombreuses autres !

Pour découvrir de nouvelles applications aux smart-contract, vous pouvez :

* Regarder l'ensemble des Applications Décentralisées existantes : [State of the Dapps](https://www.stateofthedapps.com/)
* Consulter mon flux twitter pour d'autres exemples que j'ai jugé intéressants : [@ecl_lb](https://twitter.com/ecl_lb)
* Vous tenir au courant des dernières sorties grâce aux communautés que j'ai utilisées pour réaliser ma veille (voir section [Bibliographie](bibliographie.html))
* Regarder les avancées de l'[Enterprise Ethereum Alliance](https://entethalliance.org/members/), une association de 450 entreprises cherchant à exploiter
la technologie.

À lire ensuite : [**Exemples de code Solidity ->**](exemples.html)

___
[Me contacter](mailto://leo.besancon@ecl14.ec-lyon.fr)

Suivez mon flux Twitter : [@ecl_lb](https://twitter.com/ecl_lb) !
