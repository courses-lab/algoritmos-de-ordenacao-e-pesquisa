# Como criar e preencher e ler um vetor

**Exemplo 1**
```c
#include <stdio.h>

int main(){

    int vetor[5];

    vetor[0] = 100;
    vetor[1] = 98;
    vetor[2] = 889;
    vetor[3] = 1;
    vetor[4] = 327;

    printf("%d", vetor[0]);

    return 0;
}
```

**Exemplo 2**
```c
#include <stdio.h>

int main(){

    int vetor[5]={100,98,889,1,327};

    printf("%d", vetor[0]);

    return 0;
}
```

**Exemplo 3**
```c
int main(){

    int vetor[5];
    int i;

    for(i=0; i<5; i++){
        printf("Informe numero: ");
        scanf("%d", &vetor[i]);
    }
    return 0;
}
```

**Exemplo 4**
```c
#include <stdio.h>

int main(){

    int tam, i;

    printf("Entre com o tamanho do vetor: ");
    scanf("%d", &tam);

    int vetor[tam];

    for(i=0; i<tam; i++){
        vetor[i]=rand()%100;
    }

    for(i=0; i<tam; i++){
        printf("Valor Indice %d: %d\n", i, vetor[i]);
    }

    return 0;
}
```