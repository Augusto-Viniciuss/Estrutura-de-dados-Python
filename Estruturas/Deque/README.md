## Estrutura de dados deck ou deque
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

