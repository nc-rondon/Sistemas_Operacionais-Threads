# Sistemas_Operacionais Memória
### 1.Considerando a estrutura de dados celula, crie três instâncias do objeto célula (três valores na lista); 
```   ```
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
```
### 6.Calcule o máximo de elementos possíveis na fila, considerando a memória disponível no computador.
```   ```
