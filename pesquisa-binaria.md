# Pesquisa Binária

```c
#include <stdio.h>
#include <stdbool.h>

int main(){

    // declaração de variaveis
    int tamanho,i,numero;
    int contadorA, contadorB, num, aux, busca, inicial, ultimo, meio;
    int posicao = 0;
    bool naoEncontrado;

    // pergunta ao usuário o tamanho do vetor
    printf("Informe o tamanho do vetor: ");
    scanf("%d", &tamanho);

    // insere no vetor o tamanho informado
    int vetor[tamanho];

    // preenche o vetor com numeros aleatórios
    for(i=0; i<tamanho; i++){
        vetor[i]=rand()%10;
    }

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
     return 0;
}

```