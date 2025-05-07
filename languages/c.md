---
name: C
---

# C

## Understand C pointer with examples

The program used :

```c
#include <stdio.h>

int main(){
    int number = 7;
    int *pointerTOnumber = &number;
    printf("%%d number = %d\n", number);
    printf("%%p number = %p\n", number);
    printf("%%d &number = %d\n", &number);
    printf("%%p &number = %p\n", &number);
    printf("%%d pointerTOnumber = %d\n", pointerTOnumber);
    printf("%%p pointerTOnumber = %p\n", pointerTOnumber);
    printf("%%d &pointerTOnumber = %d\n", &pointerTOnumber);
    printf("%%p &pointerTOnumber = %p\n", &pointerTOnumber);
    printf("%%d *pointerTOnumber = %d\n", *pointerTOnumber);
    printf("%%p *pointerTOnumber = %p\n", *pointerTOnumber);
}
```

> Notez que `%%` est utilisé pour afficher que `%`

Le résultat :

```c
%d number = 7                            //valeur de number sous forme décimale
%p number = 0x7                          //valeur de number sous forme Hexa car %p
%d &number = -1104070188                 //valeur de l'adresse de number sous forme décimale
%p &number = 0x7ffdbe3139d4              //valeur de l'adresse sous forme hexa car %p
%d pointerTOnumber = -1104070188         //valeur de l'adresse de number sous forme décimale
%p pointerTOnumber = 0x7ffdbe3139d4      //valeur de l'adresse de number sous forme hexa car %p
%d &pointerTOnumber = -1104070184        //valeur de l'adresse du pointeur sous forme décimale
%p &pointerTOnumber = 0x7ffdbe3139d8     //valeur de l'adresse du pointeur sous forme hexa car %p
%d *pointerTOnumber = 7                  //valeur pointée par le pointeur (donc celle de number) sous forme décimale
%p *pointerTOnumber = 0x7                //valeur pointée par le pointeur (donc celle de number) sous forme hexa car %p
```

> Caption:
>
> - `&` : On peut donc lire "**`l'adresse de`**"
> - `*` : "**`la valeur pointée par`**"
> - Accéder à une valeur avec `*` s'appelle un déréférencement

---

## Compilation

| Entrée |       Nom       | Sortie |
| :----: | :-------------: | :----: |
|  `.c`  |  Préprocesseur  |  `.i`  |
|  `.i`  |   Compilateur   |  `.s`  |
|  `.s`  |   Assembleur    |  `.o`  |
|  `.o`  | Éditeur de lien | `.out` |

---

## Vocabulaire

- Une `fonction` renvoie une valeur
- Une `procédure` prend en argument un pointeur et remplit le pointeur

---

## Paramètre de main en C

`argv[0]` contiendra tout le temps le nom du programme

```c
int main(int argc, char *argv[]){
    for(int o=0; o < argc; o++){
        printf("Argument %d : %s\n", o, argv[o]);
    }
    return 0;
}
```

---

## GCC useful options

- `-Wall` : This enables all the warnings about constructions that some users consider questionable, and that are easy to avoid (or modify to prevent the warning), even in conjunction with macros.

- `-E` : Stop after the preprocessing stage; do not run the compiler proper. The output is in the form of preprocessed source code, which is sent to the standard output

- `-D DEBUG` : Predefine name as a macro, with definition 1.

- `-E` : Affiche la sortie du préprocesseur

- `-g` : Met des points de debug

- `-l` : Mettre une librairie

- `-v` : Print (on standard error output) the commands executed to run the stages of compilation.

- `-save-temps` : Store the usual "temporary" intermediate files permanently

- `-c` : Créer des fichiers objets

- `-fno-builtin` : Don't recognize built-in functions that do not begin with __builtin_ as prefix. (see below)

## Note

```c
#include <stdio.h>

int main()
{
    // imagine you made a mistake a write 11
    // possible infinite loop if "a" and "i" and next to each other in memory
    unsigned char a[10], i;
    for (i = 0; i < 11; i++)
    {
        a[i] = 0;
    }
    // for (i = 0; i < 10; i++)
    // {
    //     printf("%d", a[i]);
    // }
    return 0;
}
```

> from [https://www.youtube.com/watch?v=443UNeGrFoM](https://www.youtube.com/watch?v=443UNeGrFoM)

## C Donut

- [https://www.youtube.com/watch?v=DEqXNfs_HhY](https://www.youtube.com/watch?v=DEqXNfs_HhY)
- [https://www.a1k0n.net/2011/07/20/donut-math.html](https://www.a1k0n.net/2011/07/20/donut-math.html)
- compile with `gcc donut.c -lm -o donut && ./donut`

## Valgrind

```sh
gcc main.c -o main.out -Wall -ggdb3
valgrind --leak-check=full --show-leak-kinds=all --track-origins=yes --verbose --log-file=out.txt ./main.out # you can add args
```
