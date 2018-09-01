---
layout: post.html
title: La blockchain est elle vraiement une révolution technologique ?
subtitle : "Il y a 6 technologies qui sont à la base de la plupart des blockchains : cryptage asymetrique 1977, les fonctions de hachage 2001, les arbres de Merkle 1979, les bases de données clé-valeur 1979, les protocoles de communication P2P 1999, la Preuve de Travail 1993. Elles sont assez anciennes et on peut même se demander pourquoi la blockchain n'a pas été inventé avant !"
tags: blockchain
masthead-img: 9441458909sqcsqs461.png
issuedate: 10 09 2017
---

Il y a 6 technologies qui sont à la base de la plupart des blockchains. Elles sont assez anciennes et on peut même se demander pourquoi la blockchain n'a pas été inventé avant !

Dans cet article nous passons en revue chacune de ces technologies et du role qu'elles jouent dans la blockchain : 

1. **Cryptage asymetrique** : utilisé pour signer les transactions de la blockchain,
2. **Fonctions de hachage** : utilisées pour vérifier l'intégrité des transactions enregistrées et pour masquer les clés publiques,
3. **Arbres de Merkle** : utilisés pour vérifier les paiements d'une manière sécurisée sans avoir à parcourir l'intégralité de tout le registre de la blockchain,
4. **Bases de données clé-valeur** : utilisé pour rechercher si une transaction a déjà été dépensée et pour ajouter une nouvelle transaction,
5. **Protocoles de communication P2P** : le protocole de communication P2P permet de mettre tous les membres en réseau, sans aucune entitée centralisatrise, 
6. **Preuve de Travail (PoW)** : utilisé pour parvenir à un consensus sur la validité des transactions enregistrées et distribuées.

---

## 1. Cryptage asymetrique (Asymmetric Encryption)

**Le cryptage asymétrique est utilisé pour signer les transactions de la blockchain.** Les signatures cryptées asymétriquement ont des propriétés exceptionnelles :

1. elles prouvent que le signataire a eu accès à la clé privée
1. la clé publique n'a pas besoin d'être revelée
1. elles sont facile à vérifier, mais impossible à corrompre

La blockchain Bitcoin utilise les paramètres [secp256k1](https://en.bitcoin.it/wiki/Secp256k1) de l'Algorithme de signature numérique à clé publique ECDSA (Elliptic Curve Digital Signature Algorithm). ECDSA a été inventé en 1985 et est devenu une norme ISO, ANSI, IEEE et FIPS en 1998-2000. L'avantage majeur d'ECDSA sur RSA est que ECDSA utilise des clés et des signatures beaucoup plus petites pour un même niveau de sécurité. En d'autres termes, Bitcoin aurait été possible avec RSA qui a été inventé en **1977** !

<a href="http://jrruethe.github.io/blog/2014/10/25/cryptography-primer/"><img class="img-shadow mx-auto d-block" src="/assets/img/asymencsnap894356.png" alt="cryptage asymetrique"></a>

---

## 2. Fonctions de hachage (Hash Functions)

**Les fonctions de hachage sont utilisées pour vérifier l'intégrité des transactions enregistrées dans le registre de la blockchain et pour masquer les clés publiques.**

Les fonctions de hachage utilisent des données d'entrée de taille arbitraire et créent, de façon déterministe, une sortie de taille fixe (généralement inférieure à la taille d'entrée) ressemblant à des données aléatoires. Une propriété clé d'une fonction de hachage est sa capacité à [résister à la collision](https://fr.wikipedia.org/wiki/R%C3%A9sistance_aux_collisions).

<a href="https://fr.wikipedia.org/wiki/Fonction_de_hachage"><img class="img-shadow mx-auto d-block" src="/assets/img/520px-Hash_function_fr.svg.png" alt="principe hash"></a>

Chaque transaction dans chaque bloc de Bitcoin est représentée par 64 caractères hexadécimaux. Cette chaîne de caractère est calculée de manière déterministe en sérialisant les contenus des transactions en octets, puis en hachant ces octets (deux fois) à l'aide de l'algorithme SHA-256. Le résultat est donc le _hash_ de la transaction, appelé son empreinte. La probabilité d'avoir deux transactions avec la même _empreinte_ est très très faible.

De fait, cette empreinte est très pratique pour vérifier l'intégrité des transactions enregistrées dans le registre de la blockchain. Tout comme une signature asymétrique ne peut pas être modifiée par quelqu'un de malhonnête, le contenu d'une transaction ne peut pas être altéré. Cela garantit à chaque membre du réseau que leur version du registre des transactions est la même que celle de tous les autres membres.

Les fonctions de hachage sont aussi utilisées dans la blockchain Bitcoin pour hacher les clés publiques utilisées pour calculer les adresses des transactions.

L'algorithme SHA-256 a été publié pour la première fois en **2001**.

---

## 3. Arbres de Merkle (Merkle Trees)

**Les arbres de Merkle sont utilisés pour vérifier les paiements d'une manière sécurisée sans avoir à parcourir l'intégralité de tout le registre de la blockchain.**

La blockchain Bitcoin utilise un arbre de Merkle pour empiler toutes les transactions dans le registre. L'arbre de Merkle est une structure de données qui contient uniquement un résumé d'un grand volume d'informations. Ils permettent de vérifier l'intégrité d'une partie seulement d'un fichier.

Cette caractéristique est utilisée dans les porte-monnaie Bitcoin installés sur les smartphone. Cela permet de vérifier les paiements d'une manière sécurisée sans avoir à stocker les 100 Giga-Octets et plus de tout le registre de la blockchain.

<a href="https://www.weusecoins.com/what-is-a-merkle-tree/"><img class="img-shadow mx-auto d-block" src="/assets/img/what-is-a-merkel-tree.jpg" alt="what is a merkle tree"></a>

L'arbre de Merkle Tree a été breveté en **1979** et est utilisé dans des systèmes de fichiers distribués comme IPFS, des systèmes de partage de fichiers comme BitTorrent, ou encore les bases de données NoSQL comme Cassandra.

---

## 4. Bases de données clé-valeur (Key-Value Database)

Pour éviter les doubles dépenses (un risque inhérent au concept de registre distribué d'une blockchain), vous devez pouvoir effectuer rapidement les deux opérations de base de données suivantes :

- Recherche si une transaction a déjà été dépensée
- Ajouter une nouvelle transaction

Alors que les bases de données NoSQL ont pris de l'ampleur au cours des dernières années (en raison principalement de leur capacité à absorber des gros volumes de données), il est important de se rappeler que les bases de données NoSQL datent réellement d'avant les bases de données relationnelles.

La blockchain Bitcoin a été lancé initialement avec BerkeleyDB, sorti en 1994. 'dbm', le principe de stockage clé-valeur qui a inspiré BerkeleyDB, a été publié en **1979**.

<a href="https://blog.barthe.ph/2014/07/23/compute-bitcoin-balance-nodejs/"><img class="img-shadow mx-auto d-block" src="/assets/img/btc_keypool_wallet.png" alt="stockage clé-valeur"></a>

---

## 5. Protocole de communication P2P (P2P communication Protocol)

**Le protocole de communication P2P permet de mettre tous les memebres en réseau dans aucune entitée centralisatrise.**

Des applications qui communiquent directement entre elles (par opposition à la communication avec un serveur) est assez rare pour la plupart des applications que nous utilisons quotidiennement. Cependant, ce n'est pas nouveau. Napster sorti en **1999** est probablement le réseau P2P le plus connu, mais USENET était apparu 20 ans avant.

Le réseau Internet est un excellent réseau pour les protocoles P2P. Le protocole Gossip est utilisé dans de nombreuses bases de données NoSQL, comme Amazon Dynamo, Cassandra et Riak.

<img class="img-shadow mx-auto d-block" src="/assets/img/6XGsvJkpPo51HlPVHxFQdddd.png" alt="stockage clé-valeur">

---

## 6. Preuve de travail (Proof Of Work)

**La blockchain Bitcoin utilise la preuve de travail pour parvenir à un consensus sur la validité des transactions enregistrées et distribuées.**

La Preuve du travail (PoW) est une utilisation intelligente des fonctions de hachage. Cela fonctionne en calculant l'empreinte d'un message, combinés à plusieurs nombres arbitraires (appelés _nonces_), jusqu'à ce que vous trouviez une empreinte qui réponde à un critère rare. Étant donné que chaque empreinte est peu susceptible de satisfaire à ce critère, la spécification d'un critère difficile à atteindre, comme par exemple une empreinte qui commence avec plusieurs zéros, est un moyen de prouver que quelqu'un a utilisé de la puissance de calcul. Le premier qui trouve la solution pour valider une nouvelle transaction est récompensé.

C'est la pierre angulaire de tout réseau distribué et ouvert, sans système d'authentification ou d'autorisation, fondé sur l'anonymat et où les membres sont tous méfiants les uns envers les autres.

Certaines personnes trouvent que la preuve de travail est inefficace, parce que le réseau Bitcoin dépense d'énormes ressources informatiques exclusivement pour valider les transactions.

La preuve de travail a été inventé en **1993**, mais a été rendu célèbre en 1997 par Hashcash d'Adam Back.

<a href="/assets/img/what-is-proof-of-work.png">Voir l'infographie</a>

---

## Technologie blockchain

La blockchain est une technologie en elle même, résultant de la combinaison de ces différentes technologie existantes depuis plusieurs dizaines d'années. C'est une technologie complexe, avec ses propres challenges comme la scalabilité, la confidentialité où encore la question du coût des transactions.

Ethereum que certain appellent la blockchain 2.0 est une première évolution qui est apparu très rapidement après la blockchain Bitcoin. Plus récemment le concept de 'Tangle' proposé par IOTA laisse présager une nouvelle révolution dans la technologie blockchain, en faisant disparaître la chaîne ! A suivre.

---

## <small>_Notes et Références_</small>

_Cet article s'inspire d'un [article publié initialement sur le blog de Paxos](https://eng.paxos.com/the-blockchain-is-evolutionary-not-revolutionary)._

- [blockchain explained (pdf)](https://www.niceideas.ch/blockchain_explained.pdf)
- [Blockchain 2.0 - From Bitcoin Transactions to Smart Contract](https://www.niceideas.ch/roller2/badtrash/entry/blockchain-2-0-from-bitcoin)
- [Tout savoir sur le #bitcoin et la #blockchain](https://fr.slideshare.net/vchriqui/tout-savoir-sur-le-bitcoin-et-la-blockchain)
- [What is a merkle tree](https://www.weusecoins.com/what-is-a-merkle-tree/)
- [Mastering Bitcoin](http://chimera.labs.oreilly.com/books/1234000001802)
- [Cryptographie asymétrique](https://fr.wikipedia.org/wiki/Cryptographie_asym%C3%A9trique)
- [Fonctions de hachage](https://fr.wikipedia.org/wiki/Fonction_de_hachage)
- [Bitcoin Hash Functions explained](https://www.coindesk.com/bitcoin-hash-functions-explained/)
- [Arbres de Merkle](https://fr.wikipedia.org/wiki/Arbre_de_Merkle)
- [Key-Value database](https://en.wikipedia.org/wiki/Key-value_database)
- [Bitcoin comment ça marche et pourquoi c'est une révolution](https://fr.slideshare.net/straumat/bitcoin-comment-a-marche-et-pourquoi-cest-une-rvolution)
