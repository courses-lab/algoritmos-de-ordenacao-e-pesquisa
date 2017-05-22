# Pesquisa Sequencial

Na Pesquisa sequencial, buscamos um valor dentro de um array comparnado-o com cada valor presente em cada posição, seguindo a sequência das posições do vetor, das primeira até a última.

<img src="images/binary-and-linear-search-animations" alt="Pesquisa Sequencial">

```c
#include <stdio.h>

int main(){

    // declaração de variaveis
    int tamanho,i,numero;
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

    // pergunta o valor que o usuário deseja pesquisar
    printf("Informe valor que sera pesquisado: ");
    scanf("%d", &numero);

    // realiza a pesquisa
    while( (posicao < 10) && (vetor[posicao] != numero) ){
        posicao++;
    }

    // exibe a quantidade de tentativas realizadas
    printf("Tentativa: %d\n", posicao+1);

    // exibe o vetor gerado
    for(i=0; i<10; i++){
        printf("Indice: %d - Valor: %d\n",i,vetor[i]);
    }

    // exibe o resultado na tela
    if(vetor[posicao] == numero){
        printf("Numero da posicao: %d", posicao);
    } else {
        printf("Numero nao encontrado!");
    }

    return 0;
}
```