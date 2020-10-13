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
