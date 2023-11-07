# Sistemas_Operacionais Memória
### 1.Considerando a estrutura de dados celula, crie três instâncias do objeto célula (três valores na lista); 
```
int main() {
    celula *head = NULL;  // Inicialmente, a lista está vazia

    // Adicionando três elementos à lista
    celula *c1 = (celula *)malloc(sizeof(celula));
    c1->conteudo = 10;
    c1->prox = head;
    head = c1;

    celula *c2 = (celula *)malloc(sizeof(celula));
    c2->conteudo = 20;
    c2->prox = head;
    head = c2;

    celula *c3 = (celula *)malloc(sizeof(celula));
    c3->conteudo = 30;
    c3->prox = head;
    head = c3;
  ```
### 2.Construa uma função que imprima todos os valores da lista; 
```
void imprimirLista(celula *head) {
    celula *atual = head;
    while (atual != NULL) {
        printf("%d ", atual->conteudo);
        atual = atual->prox;
    }
    printf("\n");
}
  ```
### 3.Calcule a quantidade de memória gasta por cada instância da célula
```  
size_t tamanhoCelula() {
    return sizeof(celula);
}
```
### 4.Construa uma função que remove os elementos da lista;
``` 
void removerElemento(celula **head, int valor) {
    celula *anterior = NULL;
    celula *atual = *head;

    while (atual != NULL && atual->conteudo != valor) {
        anterior = atual;
        atual = atual->prox;
    }

    if (atual == NULL) {
        // Valor não encontrado na lista
        return;
    }
}

```
### 5.Incremente sua função liberando a memória quando um elemento é liberado;
``` 
if (anterior == NULL) {
        // O elemento a ser removido é o primeiro da lista
        *head = atual->prox;
    } else {
        anterior->prox = atual->prox;
    }

    free(atual);
// função completa no código
```
### 6.Calcule o máximo de elementos possíveis na fila, considerando a memória disponível no computador.
``` size_t tamanho_celula = tamanhoCelula();
    size_t memoria_disponivel_gb = 8;  // 8 GB de memória

    // Converter GB para bytes (1 GB = 1024 MB, 1 MB = 1024 KB, 1 KB = 1024 bytes)
    size_t memoria_disponivel = memoria_disponivel_gb * 1024 * 1024 * 1024;

    size_t numero_maximo_elementos = memoria_disponivel / tamanho_celula;

    printf("Número máximo de elementos possíveis na fila: %lu\n", numero_maximo_elementos);
  ```
