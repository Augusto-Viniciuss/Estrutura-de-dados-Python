# Estrutura de dados implementadas em Python

### Estrutura de dados Pilha
### Segue a filosofia FILO "first in last out"

```py
class Pilha:
    def __init__(self):
        self.pilha = []
        self.tamanhoDaPilha = 0
    
    def insereNaPilha(self, elemento):
        self.pilha.append(elemento)
        self.tamanhoDaPilha += 1
        
    def removeDaPilha(self):
        if not self.pilhaEstaVazia():
            self.pilha.pop(-1)
            self.tamanhoDaPilha -= 1
            
    def topoDaPilha(self):
        if not self.pilhaEstaVazia():
            return self.pilha[-1]
        else:
            return None
        
    def pilhaEstaVazia(self):
        if self.tamanhoDaPilha == 0:
            return True
        else:
            return False
    
    def tamanhoDaPilha(self):
        return self.tamanhoDaPilha
    
    def retornaPilha(self):
        return self.pilha
 ```
 
### Estrutura de dados Fila
### Segue a filosofia FIFO "First in first out"

```py
class Fila:
    def __init__(self):
        self.fila = []
        self.tamanhoDaFila = 0
        
    def insereNaFila(self, elemento):
        self.fila.append(elemento)
        self.tamanhoDaFila += 1
    
    def removeDaFila(self):
        if not self.filaEstaVazia():
            self.fila.pop(0)
            self.tamanhoDaFila -= 1
            
    def primeiroDaFila(self):
        if not self.filaEstaVazia():
            return self.fila[0]
        else:
            None
        
    def ultimoDaFila(self):
        if not self.filaEstaVazia():
            return self.fila[-1]
        else:
            return None    
    
    def filaEstaVazia(self):
        if self.tamanhoDaFila == 0:
            return True
        else:
            return False
        
    def tamanhoDaFila(self):
        return self.tamanhoDaFila
    
    def retornaFila(self):
        return self.fila
```

### Estrutura de dados deck ou deque
### Segue uma filosofia de uma Fila de duas pontas, onde da pra inserir e remover da frente e de trás da fila

```py
class Deque:
    def __init__(self):
        self.deque = []
        self.tamanhoDoDeque = 0
        
    def insereNaFrente(self, elemento):
        self.deque.insert(0, elemento)
        self.tamanhoDoDeque += 1
        
    def insereAtras(self, elemento):
        self.deque.append(elemento)
        self.tamanhoDoDeque += 1
        
    def removeDaFrente(self):
        if not self.dequeEstaVazio():
            self.deque.pop(0)
            self.tamanhoDoDeque -= 1
            
    def removeDeTras(self):
        if not self.dequeEstaVazio():
            self.deque.pop(-1)
            self.tamanhoDoDeque -= 1
        
    def primeiroDoDeque(self):
        if not self.dequeEstaVazio():
            return self.deque[0]
        else:
            return None
        
    def ultimoDoDeque(self):
        if not self.dequeEstaVazio():
            return self.deque[-1]
        else:
            return None
    
    def dequeEstaVazio(self):
        if self.tamanhoDoDeque == 0:
            return True
        else:
            return False
        
    def tamanhoDoDeque(self):
        return self.tamanhoDoDeque
    
    def retornaDeque(self):
        return self.deque
```

### Estrutura de dados Listas encadeadas
### Segue a filosofia de que um elemento guarda a referência de seu próximo para linkar a lista

```py
class No:
    def __init__(self, nome):
        self.nome = nome
        self.proximo = None
        
    def retornaNome(self):
        return self.nome
    
    def mudaNome(self, nome):
        self.nome = nome
        
    def retornaProximo(self):
        return self.proximo
    
    def mudaProximo(self, proximo):
        self.proximo = proximo
        
class ListaEncadeada:
    def __init__(self):
        self.primeiro = None
        self.ultimo = None
        self.tamanhoDaLista = 0
        
    def insereNaLista(self, indice, elemento):
        
        no = No(elemento)
        
        if self.listaEstaVazia():
            self.primeiro = no
            self.ultimo = no
        else:
            if indice == 0:
                no.mudaProximo(self.primeiro)
                self.primeiro = no
            elif indice >= self.tamanhoDaLista:
                self.ultimo.mudaProximo(no)
                self.ultimo = no
            else:
                
                noAnterior = self.primeiro
                noAtual = self.primeiro.retornaProximo()
                indiceAtual = 1
                
                while noAtual != None:
                    if indiceAtual == indice:
                        no.mudaProximo(noAtual)
                        noAnterior.mudaProximo(no)
                        break
                        
                    noAnterior = noAtual
                    noAtual = noAtual.retornaProximo()
                    indiceAtual += 1
                    
        self.tamanhoDaLista += 1
        
        
    def removeDaLista(self, indice):
        if not self.listaEstaVazia() and indice >= 0 and indice < self.tamanhoDaLista:
            
            if self.primeiro.retornaProximo() == None:
                self.primeiro = None
                self.ultimo = None
            elif indice == 0:
                self.primeiro = self.primeiro.retornaProximo()
            else:
                noAnterior = self.primeiro
                noAtual = self.primeiro.retornaProximo()
                indiceAtual = 1
                
                while noAtual != None:
                    if indiceAtual == indice:
                        noAnterior.mudaProximo(noAtual.retornaProximo())
                        break
                        
                    noAnterior = noAtual
                    noAtual = noAtual.retornaProximo()
                    indiceAtual += 1
                        
                    
            
            self.tamanhoDaLista -= 1
            
    def listaEstaVazia(self):
        if self.tamanhoDaLista == 0:
            return True
        else:
            return False
        
    def tamanhoDaLista(self):
        return self.tamanhoDaLista  
        
    def primeiroDaLista(self):
        return self.primeiro
    
    def ultimoDaLista(self):
        return self.ultimo
    
    def mostraLista(self):
        noAtual = self.primeiro
    
        while noAtual != None:
            print(noAtual.retornaNome(), end= ", ")
            noAtual = noAtual.retornaProximo()
```

### Estrutura de dados Árvore binária de busca
### Ainda estou estudando
