# TP05 - Structures itératives - Compléments
**STS 1CIEL** - Cette fois-ci nous allez plus loin sur l'utilisation des boucles et boucles imbriquées afin de parcourir des tableaux et faire des dessins sur le terminal.

Ce repository est un projet CLion dans lequel vous trouverez un certain nombre de fichiers `.cpp` qui vont vous permettre de coder chaque exercice demandé. Une fois terminé il suffira de faire un commit, puis un push vers GitHub afin de rendre votre travail.


## Exo1 - Damier de nombres

Réaliser un programme qui affiche un damier de forme carrée, de côté de longueur $n>0$ et rempli alternativement du nombre 4 et du nombre 2. La case en haut à gauche sera toujours 4. Par exemple, pour $n=7$, le damier aura l'allure suivante :

```text
4 2 4 2 4 2 4
2 4 2 4 2 4 2
4 2 4 2 4 2 4
2 4 2 4 2 4 2
4 2 4 2 4 2 4
2 4 2 4 2 4 2
4 2 4 2 4 2 4
```

Il est possible de coder l'exercice de plusieurs façons. On pourra imaginer que la grille est numérotée par ligne et par colonne et on remarquera que tous les 4 de la grille sont à des indices de ligne et de colonne qui ont toujours la même parité (soit les deux indices sont pairs, soit les deux indices sont impairs).

## Exo2 - Liste de nombres premiers

### Première étape
Écrire un programme pour savoir si un nombre n donné est premier ou pas.

**Rappel** : Un nombre est premier s'il n'est divisible que par 1 et lui-même. 

▶︎ [Wikipédia Nombre Premier](https://fr.wikipedia.org/wiki/Nombre_premier)

### Deuxième étape
Écrire un code qui affiche les N premiers nombres premiers. (et non pas les nombres premiers inférieurs ou égaux à N)


## Exo3 - Nombres de Harshad
On dit qu'un entier `n>0` est un nombre de Harshad s'il est divisible par la somme de ses chiffres. Par exemple, 42 est un nombre de Harshad car la somme de ses chiffres est 6 et 42 est un multiple de 6. En revanche, 32 n'est pas un nombre de Harshad puisque 32 n'est pas un multiple de 5.

Déterminer la liste des nombres de Harshad ayant 1, 2 ou 3 chiffres (on trouvera une liste de 212 entiers). On utilisera 3 boucles `for` imbriquées et un vecteur pour stocker ces nombres.

## Exo 4 - Sapin de Noël

### 1. Juste le sapin
Nous souhaitons créer un programme qui affiche sur la console un sapin de Noël dont l’entier `n` définit sa hauteur. Le corps du sapin sera formé de caractères `.`

Par exemple pour `n=5` , nous obtenons sur la console :

```text
    .
   ...
  .....
 .......
.........
```

### 2. On ajoute l'étoile !

Nous souhaitons ajouter une étoile en haut de notre sapin! L'étoile sera représentée par `*` **et apparaîtra seulement si le booléen `etoile` vaut `true`**.

```text
    *
   ...
  .....
 .......
.........
```

### 3. On ajoute le pied !

À présent nous souhaitons ajouter un pied en bas du sapin, celui-ci sera formé des caractères : `| |` et centré sur la cime, **peut importe la taille du sapin, la taille du pied ne changera pas**. Le pied apparaîtra seulement si le booléen `pied` vaut `true`.

```text
    *
   ...
  .....
 .......
.........
   | |
```

### 4. On ajoute les boules !

Pour terminer ajoutons les boules au sapin! Sur chaque étage vous ajouterez un caractère `o` une colonne sur deux. Les boules devrons s'afficher seulement si le booléen `boules` vaut `true`.

Après affichage du sapin vous devrez afficher à l'écran le nombre de boules présentes sur celui-ci.

```text
    *
   .o.
  .o.o.
 .o.o.o.
.o.o.o.o.
   | |

Il y a 10 boules sur ce beau sapin.
```

## Exo 5 - Construction et affichage d'un vecteur 2D

1. Demandez à l'utilisateur la taille `n` du vecteur
2. Créez et remplissez d'entiers compris entre 0 et 9 un vecteur 2D, de côté `n`. 
3. Affichez le tableau ainsi créé.

Exemple pour `n=4` :

```text
2 9 6 1
3 5 1 0
1 3 7 7
1 2 5 6
```

Nous donnons ci-dessous un exemple d'utilisation de la bibliothèque `random` afin de générer un entier aléatoire compris entre 1 et 9 :

```cpp
#include <iostream>
#include <random>

int main() {
    // Initialisation du générateur de nombres aléatoires
    std::random_device rd;  // Génère une graine aléatoire
    std::mt19937 gen(rd()); // Générateur de nombres aléatoires Mersenne Twister
    std::uniform_int_distribution<> dis(1, 9); // Distribution uniforme entre 1 et 9

    // Génération d'un nombre aléatoire
    int random_number = dis(gen);

    // Affichage du nombre aléatoire
    std::cout << "Nombre aléatoire entre 1 et 9: " << random_number << std::endl;

    return 0;
}
```

## Exo 6 - Test matrice symétrique

Soit une matrice (vecteur 2D) M à `n` lignes, `n` colonnes stockée dans un vecteur de `n` vecteurs à `n` éléments entiers.

M est symétrique si pour tout `i` et `j` indices respectivement de lignes et colonnes on a `M[i][j] = M[j][i]`.

Par exemple la matrice suivante est symétrique : 
```txt
1 6 8 3 
6 6 5 1
8 5 9 7
3 1 7 7
```
tandis que celle-ci ne l'est pas :
```txt
1 6 8 3 
3 6 5 1
6 4 9 7
9 6 8 7
```    
Écrire un code indiquant si une matrice est symétrique ou non.


## Exo 7 - Construction matrice symétrique

Cette fois-ci il s'agit de construire une matrice symétrique de côté `n` donné par l'utilisateur, le contenu de cette matrice sera remplie de manière aléatoire avec des entiers tirés entre 0 et 9. Nous rappelons que pour q'une matrice `M` soit symétrique elle doit respecter la propriété `M[i][j] = M[j][i]`.

## Exo 8 - Triangle de pascal

Réaliser un programme qui affiche les n (n >=2) premières lignes du triangle de Pascal.
Pour n = 10, on obtient :

![](figures\trianglePascal.jpg)


l'élément situé en ligne i et colonne j, noté $t_{i,j}$ vaut la somme de celui situé en ligne i-1,colonne j avec celui situé en ligne i-1 et colonne j-1. 

cad : $t_{i,j}$ = $t_{i-1,j}$ + $t_{i-1,j-1}$