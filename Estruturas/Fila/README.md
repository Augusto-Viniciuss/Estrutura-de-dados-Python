## Estrutura de dados Fila
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

