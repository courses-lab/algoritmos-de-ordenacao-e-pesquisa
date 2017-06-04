# Pesquisa Sequencial

Na Pesquisa sequencial, buscamos um valor dentro de um array comparnado-o com cada valor presente em cada posição, seguindo a sequência das posições do vetor, das primeira até a última.

- É o método de pesquisa mais simples;
- Frequentemente utilizado para varrer vetores;
- Efeciente quando o conjunto de dados é pequeno;

**Desvantagens**

- Pode ser ineficiente quando  conjunto de dados é grande;
- Não é indicado para pesquisas onde os dados estão ordenados.

<img src="images/binary-and-linear-search-animations.gif" alt="Pesquisa Sequencial">

```c
#include <stdio.h>

int main(){

    int tamanho,i,numero;
    int posicao = 0;

    //pergunta ao usuario o tamanho do vetor
    printf("Informe o tamanho do vetor: ");
    scanf("%d", &tamanho);

    //insere no vetor o tamanho informado
    int vetor[tamanho];

    // preenche o vetor com números aleatórios
    for(i=0; i<=tamanho; i++){
        vetor[i] = rand()%100;
    }

    // pergunta o valor que o usuário deseja pesquisar
    printf("Qual eh o valor a ser pesquisado? ");
    scanf("%d", &numero);

    // realiza a pesquisa
    while( (posicao < tamanho) && (vetor[posicao] != numero) ){
        posicao++;
    }

    // exibe o vetor gerado
    for(i=0; i<tamanho; i++){
       printf("Indice: %d - Valor: %d\n", i,vetor[i]);
    }

    // exibe o resultado na tela
    if(vetor[posicao] == numero){
        printf("Numero da posicao: %d\n", posicao);
    } else {
        printf("Numero nao encontrado!\n");
    }

    // exibe a quantidade de tentativas realizadas
    printf("Tentativa: %d\n", posicao+1);

    return 0;
}
```