# Quick Sort

```c
#include<stdio.h>

void quickSort(int valor[], int esquerda, int direita){
    int i,j,x,y;
    i = esquerda;
    j = direita;
    x = valor[(esquerda + direita) / 2];

    while(i <= j){
        while(valor[i] < x && i < direita){
            i++;
        }

        while(valor[j] > x && j > esquerda){
            j--;
        }

        if(i <= j){
            y = valor[i];
            valor[i] = valor[j];
            valor[j] = y;
            i++;
            j--;
        }
    }

    if(j > esquerda){
        quickSort(valor, esquerda, j);
    }

    if(i < direita){
        quickSort(valor, i, direita);
    }
}

int main(){

    // declaração de variaveis
    int tamanho,y;
    int esquerda, direita;

    // pergunta ao usuário o tamanho do vetor
    printf("Informe o tamanho do vetor: ");
    scanf("%d", &tamanho);

    // insere no vetor o tamanho informado
    int valor[tamanho];

    // preenche o vetor com numeros aleatórios
    for(y=0; y<tamanho; y++){
        valor[y]=rand()%10;
    }

    printf("**********************\n");
    printf("Vetor desordenado:\n");
    printf("**********************\n");
    for(y=0; y<tamanho; y++){
        printf("%d ",valor[y]);
    }

    esquerda = 0;
    direita = tamanho-1;

    printf("\n");
    printf("\n");

    quickSort(valor, esquerda, direita);

    printf("**********************\n");
	printf("Vetor reorganizado:\n");
	printf("**********************\n");
	for(y = 0; y < 9; ++y){
		printf(" %d ", valor[y]);
	}

    return 0;
}

```