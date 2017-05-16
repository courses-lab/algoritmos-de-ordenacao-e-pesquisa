# Insertion sort

```c
#include<stdio.h>

void insertion(int vetor[],int tamanho){
     
    // declaração de variaveis
    int i, j, eleito;

    for(i=1; i<tamanho; i++){
        eleito=vetor[i];
        j=i-1;

        while( (j>=0) && (eleito<vetor[j]) ){
            vetor[j+1] = vetor[j];
            j--;
        }
        
        vetor[j+1] = eleito;
    }

    // exibe o vetor ordenado
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
        vetor[i]=rand()%10;
    }

     printf("Vetor desordenado:\n");

    for(i=0; i<tamanho; i++){
        printf("%d ",vetor[i]);
    }

    printf("\n");
    insertion(vetor,tamanho);

    return 0;
}

```