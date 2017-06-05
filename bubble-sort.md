# Bubble sort

Bubble sort, ou ordenação por flutuação (literalmente "por bolha"), é um dos mais simples algoritmos de ordenação. A ideia é percorrer o vetor diversas vezes, a cada passagem fazendo flutuar para o topo o maior elemento da sequência. Essa movimentação lembra a forma como as bolhas em um tanque de água procuram seu próprio nível, e daí vem o nome do algoritmo.

- É um dos mais simples algoritmos de ordenação;
- Não é recomendado para situações que precisem de velocidade e operem com grandes quantidades de dados.

<img src="images/Bubble-sort-example-300px.gif" alt="Bubble sort">

**Implementação do Algoritmo em C**

```c
#include <stdio.h>

int main(){
    int i,b,j,r;
    int tamanho,aux;

    // pergunta ao usuário o tamanho do vetor
    printf("Informe o tamanho do vetor: ");
    scanf("%d", &tamanho);

     // insere no vetor o tamanho informado
    int vetor[tamanho];

    // preenche o vetor com numeros aleatórios
    for(i=0; i<tamanho; i++){
        vetor[i]=rand()%100;
    }

    for(b=tamanho-1; b>=1; b--){
        for(j=0; j<b; j++){
            if(vetor[j]>vetor[j+1]){
                aux = vetor[j];
                vetor[j] = vetor[j+1];
                vetor[j+1] = aux;
            }
        }
    }

    for(r=0; r<tamanho; ++r){
        printf("- %d ", vetor[r]);
    }

    return 0;
}

```