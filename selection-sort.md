# Selection sort

Selection sort, ou ordenação por seleção, é um algoritmo de ordenação que procura passar sempre o menor valor do vetor para a primeira posição (ou o maior dependendo da ordem requerida), depois o de segundo menor valor para a segunda posição, e assim
é feito sucessivamente com os (n-1) elementos restantes, até os últimos dois elementos.

<img src="images/Selection-Sort-Animation.gif" alt="Selection-Sort-Animation">

```c
#include<stdio.h>

void selection(int vetor[], int tamanho){
    int i,j,menor;

    for(i=0; i<(tamanho-1); i++){
      menor = i;

      for(j=(i+1); j<tamanho; j++){
        if(vetor[j] < vetor[menor]){
            menor = j;
        }
      }

      if(i != menor){
        int auxiliar = vetor[i];
        vetor[i] = vetor[menor];
        vetor[menor] = auxiliar;
      }
    }
    printf("Vetor ordenado:\n");

    for(i=0; i<tamanho; i++){
        printf("%d ",vetor[i]);
    }
}

int main(){

    // declaração de variaveis
    int tamanho,i,numero;

    // pergunta ao usuário o tamanho do vetor
    printf("Informe o tamanho do vetor: ");
    scanf("%d", &tamanho);

    // insere no vetor o tamanho informado
    int vetor[tamanho];

    // preenche o vetor com numeros aleatórios
    for(i=0; i<tamanho; i++){
        vetor[i]=rand()%100;
    }

     printf("Vetor desordenado:\n");

    for(i=0; i<tamanho; i++){
        printf("%d ",vetor[i]);
    }

    printf("\n");
    printf("\n");
    selection(vetor,tamanho);

    return 0;
}
```