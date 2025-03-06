### ES1 (2 pt)

Scrivere file c: `es1.c` che stampi con quattro chiamate alla funzione `printf()` il valore esadecimale (`%#x`) e il corrispondente indirizzo di memoria (`%p`) di ciascuno dei quattro byte del valore intero senza segno `12756`. Infine, incollare l'output del programma nel file `es1.txt` e dire se la propria macchina è di tipo BIG o LITTLE endian, argomentando brevemente i motivi della risposta.

### ES2 (2.5 pt)

Scrivere un file c: `es2.c` che implementi la funzione `inverti_stringa(char *stringa, int dim)` richiamata nel main di sotto.  

```c
int main(void){
        char stringa[10] =  "aeiou";
        printf("%s\n", stringa);
        inverti_stringa(stringa, 6);
        printf("%s\n", stringa);
        return 0;
}
```

### ES3 (0.5 pt)

Scrivere un file c: `es3.c` che dichiari una macro `DIM_MACRO` in grado di calcolare il numero di elementi di questi due vettori

```c
int main(void){
        int a[100];
        double b[50];
        size_t dim_a = DIM_MACRO(a);
        size_t dim_b = DIM_MACRO(b);

        printf("a e' un vettore di interi di %ld elementi\n", dim_a);
        printf("b e' un vettore di double di %ld elementi\n", dim_b);
}
```

### ES4 (2.5 pt)

Scrivere un file c: `es4.c` che implementi la funzione `int distanza(int a[], int x, int y, int n)` che calcoli la distranza tra gli elmenti x e y nel vettore a di n elementi. La funzione deve calcolare la distanza tra l'elemento x ed y utilizzando le seguenti due variabili locali

* `int *px`
* `int *py`

```c
int main(void){
        int a[] = {1,4,3,6,7,2,9,0,5};
        for(int i=0; i<9; i++)
                printf("%d\t", a[i]);
        printf("\n");

        int x = 3;
        int y = 9;
        int d = distanza(a, x, y, 9);
        printf("la distanza tra %d e %d e' di %d posizioni\n", x, y, d);
        return 0;
}
```

### ES5 (2.5 pt)

Copiare tutto il codice di sotto nel file `es5.c`. Compilando il codice otterrai degli errori di compilazione. Rimuovi tutti gli errori sintattici. Lanciando il programma questo andra in crash, risolvi gli errori in modo da far funzionare correttamente tutto il programma.

```c
#include<stdio.h>

int main(void){

        int a = 5;
        a++;
        int *pa;
        printf("a vale %d, a e' all'indirizzo di memoria %p\n", *pa, pa);


        // iterare il vettore con un puntatore
        int b[5] = {1,2,3,4,5};
        while(b<&b[5]){
                printf("%d\t", *b);
                b++;
        }
        printf("\n");

        // sostiuire in c la stringa miao
        char c[5] = "ciao";
        c = "miao";
        printf("%s\n", c);

        // sostituire in d la stringa miao
        char *d = "ciao";
        d[0] = 'm';
        printf("%s\n", d);

}
```

l'output corretto del programma funzionante è il seguente (ovviamente il valore dell'indirizzo di memoria di a sarà diverso)

```
a vale 6, a e' all'indirizzo di memoria 0x7ffe2ff8bc24
1       2       3       4       5
miao
miao
```

### ES6

Dato il seguente file `main.c`, completare le parti mancanti (vedi **TODO** nel codice). 

```c
#include<stdio.h>
#include<stdlib.h>
#define N 4

void accoda(int **a, int **tail);

int main(void){

        int *a[N] = {NULL};  // vettore di puntatori
        int *tail = a[0];    // puntaore all'ultimo elemento di a
        /* TODO: fai un ciclo for che richiama quattro volte la funzione accoda()
                 passando in ingresso il vettore a e l'indirizzo di memoria di tail
         */
        for(int i=0; i<N; i++)
                printf("%p\t %d\n", a[i], *a[i]);
        printf("\n");
        return 0;
}

void accoda(int *a[], int **tail){
        int *tmp = (int *)malloc(sizeof(int));
        printf("Inserisci numero: ");
        scanf("%d", tmp);
        printf("\n");

        /* TODO: fai un ciclo while (o for) che cicla fino all'ultimo elemento (*tail) di a
                 ed inserisce in coda tmp. Alla fai puntare tail all'ultimo elemento aggiunto
         */
}
```
