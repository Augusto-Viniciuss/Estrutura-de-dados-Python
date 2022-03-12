## Estrutura de dados Listas encadeadas
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

