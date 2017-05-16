# Bubble sort

```c
#include <stdio.h>

void bubble(int vetor[],int tamanho){

    // declaração de variaveis
    int i,auxiliar,trocou,contador;

    contador = tamanho;

    do {
        tamanho--;
        trocou = 0;

        for(i=0; i<tamanho; i++){
            
            if(vetor[i] > vetor[i + 1]) {
                auxiliar = vetor[i];
                vetor[i] = vetor[i+1];
                vetor[i+1] = auxiliar;
                trocou = 1;
            }            
        
        }
            

    } while(trocou);

    // exibe o vetor ordenado
    printf("Vetor ordenado:\n");

    for(i=0; i<contador; i++){
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
    bubble(vetor,tamanho);

    return 0;
}

```