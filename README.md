# **Introduction blockchain Ethereum**

## **DLT: Distributed ledger technology AKA Blockchain**

Les technologies blockchain ont résolu 2 problèmes:

- immuabilité: les données ne peuvent pas être modifiées
- processus distribué: plus de point d'autorité unique ou de point de défaillance unique (_«SPOF»_ : `single point of authority or a single point of failure`), chaque nœud travaille ensemble sur la base d'un mécanisme de consensus empêchant les acteurs malveillants.

### **Immutability**

Dans une blockchain, toutes les transactions sont stockées dans un bloc.
Chaque bloc comprend le "hachage cryptographique" du bloc précédent dans la chaîne, reliant les deux blocs, ainsi qu'un "hachage cryptographique" de toutes les transactions stockées dans le bloc.
Le «hachage cryptographique» est un «hachage» généré par une «fonction de hachage cryptographique».
La «fonction de hachage cryptographique» est une fonction à sens unique (fonction non inversible) qui mappe le contenu d'un bloc à un nombre.
Ces 2 nombres, le «hachage cryptographique» du bloc précédent et le «hachage cryptographique» de toutes les transactions confirmées dans le bloc, sont stockés dans «l'en-tête du bloc» du nouveau bloc entrant.
![blockchain](./res/blockchain.jpeg)
Ci-dessous comment ce type de processus peut être implémenté avec du code:
![code structure of blockchain](./res/codeview.jpg)
Ci-dessous un aperçu de base d'un en-tête de bloc:
![block header basic overview](./res/blockheader.png)

Ce processus confirme l '** intégrité ** du bloc, jusqu'au "bloc de genèse" original.

Si un acteur malveillant veut modifier un bloc, par exemple en modifiant le montant d'une transaction, il modifiera le «hachage» de toutes les transactions dans le bloc. Il devra donc miner à nouveau ce bloc. Le processus modifiera le bloc entier `hash`, et tous les blocs suivants auront un` hash` différent stocké dans leur en-tête pour le bloc précédent. L'acteur malveillant devra donc extraire également tous les blocs suivants basés sur le `hachage 'du bloc malveillant conçu.
L'autre protection qui empêche ce type de modifications est un mécanisme de consensus.
Les attaquants devraient contrôler 51% du réseau pour inverser les transactions qui ont déjà eu lieu dans une blockchain.
Ceci est connu sous le nom de ** 51% Attack **
Inutile de dire que c'est en fait impossible, les attaquants auraient besoin de beaucoup de puissance de calcul, et même s'ils réussissaient, cela invaliderait la confiance sur cette blockchain et les utilisateurs partiraient simplement.

### **Centralized vs Decentralized vs Distributed**

![Centralized vs Decentralized vs Distributed](./res/CDD.png)

Dans un réseau distribué, il n'y a pas un point d'autorité unique (ni même multiple).
L'objectif est d'éviter un seul point de défaillance: `SPOF`
Ainsi, des mécanismes de consensus sont utilisés pour s'assurer que chaque nœud d'un réseau distribué fonctionne ensemble, et jamais de manière malveillante.
Dans le cas d'un réseau blockchain, des mécanismes de consensus sont utilisés pour contrôler comment une transaction blockchain peut être validée, écrite dans un bloc et exécutée.

### **Consensus mechanisms**

#### **Byzantine generals problem**

https://fr.wikipedia.org/wiki/Probl%C3%A8me_des_g%C3%A9n%C3%A9raux_byzantins

#### **Proof of work: PoW**

En francçais: ** preuve de travail **.
Il s'agit de l'algorithme de consensus original.
Avec «PoW», les mineurs se font concurrence pour effectuer des transactions sur le réseau et ajouter de nouveaux blocs à la blockchain.
Les mineurs doivent résoudre un casse-tête difficile en utilisant la puissance de traitement de leur ordinateur.
Le casse-tête mathématique à résoudre consiste à trouver un numéro de hachage pour l'en-tête du bloc courant en manipulant le champ «nonce» de ce bloc.
Le numéro de hachage à trouver doit être inférieur à un hachage «cible». Le hachage «cible» est défini par une «difficulté».
! [processus d'extraction] (./ res / bitcoin_block_hashing.jpg)

Le premier mineur à résoudre le puzzle reçoit une récompense pour son travail.
Une preuve de travail est une donnée qui est difficile (coûteuse, longue) à produire mais facile à vérifier pour les autres et qui satisfait à certaines exigences.

