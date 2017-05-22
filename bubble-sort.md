# Bubble sort

Bubble sort, ou ordenação por flutuação (literalmente "por bolha"), é um dos mais simples algoritmos de ordenação. A ideia é percorrer o vetor diversas vezes, a cada passagem fazendo flutuar para o topo o maior elemento da sequência. Essa movimentação lembra a forma como as bolhas em um tanque de água procuram seu próprio nível, e daí vem o nome do algoritmo.

<img src="images/Bubble-sort-example-300px.gif" alt="Bubble sort">

```c
#include <stdio.h>
#include <stdbool.h>

void pesquisaBinaria(int vetor[], int tamanho){

    int contadorA,contadorB,aux,busca;
    int inicial, ultimo, meio;
    bool naoEncontrado;

    // ordena os valores do vetor
    for(contadorA = 0; contadorA < 10; contadorA++){
        for(contadorB = contadorA + 1; contadorB < 10; contadorB++){
            if( vetor[contadorA] > vetor[contadorB] ){
                aux = vetor[contadorB];
                vetor[contadorB] = vetor[contadorA];
                vetor[contadorA] = aux;
            }
        }
    }

    printf("Vetor ordenado. Preparado para busca binaria: ");

    // exibe na tela o vetor ordenado
    for(contadorA = 0; contadorA < 10; contadorA++){
        printf(" %d -", vetor[contadorA]);
    }

    printf("\n");

    // pergunta ao usuário qual valor deseja pesquisar
    printf("Qual o valor para busca? ");
    scanf("%d",&busca);

    inicial = 0;
    ultimo = 9;
    naoEncontrado = false;

    // esse laço divide o vetor em duas partes e dependendo do valor a ser encontrado escolhe uma das partes
    while( (inicial <= ultimo) && !(naoEncontrado) ){
        meio = (inicial + ultimo) / 2;

        if(vetor[meio] == busca){
            naoEncontrado = true;
        }

        if(vetor[meio] > busca){
            ultimo = meio - 1;
        }else{
            inicial = meio + 1;
        }
    }

    if(naoEncontrado == true){
        printf("Dado encontado na posicao %d! ", meio);
    }else{
        printf("Dado nao encontrado no vetor!");
    }
}

int main(){

    // declaração de variaveis
    int tamanho,i;
    int posicao = 0;


    // pergunta ao usuário o tamanho do vetor
    printf("Informe o tamanho do vetor: ");
    scanf("%d", &tamanho);

    // insere no vetor o tamanho informado
    int vetor[tamanho];

    // preenche o vetor com numeros aleatórios
    for(i=0; i<tamanho; i++){
        vetor[i]=rand()%10;
    }

    pesquisaBinaria(vetor, tamanho);

    return 0;
}

```