# Estrutura de dados implementadas em Python

<div>
    ## Estrutura de dados Pilha

    ```cpp
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
</div>
