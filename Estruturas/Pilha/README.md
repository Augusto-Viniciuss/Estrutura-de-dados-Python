## Estrutura de dados Pilha
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
 
