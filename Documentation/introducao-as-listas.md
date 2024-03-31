Introdução às Listas

As listas são estruturas de dados versáteis e poderosas que nos permitem armazenar e manipular coleções de elementos de forma eficiente. 

## O que são listas?

Uma lista em Python é uma coleção ordenada de elementos. Esses elementos podem ser de diferentes tipos, como números, strings, ou até mesmo outras listas. As listas são definidas utilizando colchetes `[]` e os elementos são separados por vírgulas. Vamos ver alguns exemplos:

```python
# Exemplo de lista de números
numeros = [1, 2, 3, 4, 5]

# Exemplo de lista de strings
nomes = ['Alice', 'Bob', 'Carol', 'David']

# Exemplo de lista mista
misturada = [1, 'dois', 3.0, 'quatro']
```

## Acessando os elementos de uma lista

Os elementos de uma lista são acessados utilizando índices. É importante lembrar que os índices em Python começam em 0, não em 1. Veja como acessar os elementos de uma lista:

```python
numeros = [10, 20, 30, 40, 50]

# Acessando o primeiro elemento da lista
primeiro = numeros[0]  # Retorna 10

# Acessando o terceiro elemento da lista
terceiro = numeros[2]  # Retorna 30
```

## Modificando e adicionando elementos

Podemos modificar os elementos de uma lista atribuindo novos valores a eles. Também podemos adicionar novos elementos utilizando o método `append()` ou inserindo elementos em uma posição específica utilizando o método `insert()`. Veja alguns exemplos:

```python
numeros = [1, 2, 3]

# Modificando o segundo elemento
numeros[1] = 10  # Agora numeros é [1, 10, 3]

# Adicionando um novo elemento ao final da lista
numeros.append(4)  # Agora numeros é [1, 10, 3, 4]

# Inserindo um novo elemento na segunda posição
numeros.insert(1, 5)  # Agora numeros é [1, 5, 10, 3, 4]
```

## Removendo elementos

Para remover elementos de uma lista, podemos utilizar o método `pop()` para remover um elemento específico pelo seu índice, ou o método `remove()` para remover um elemento pelo seu valor. Veja como funciona:

```python
numeros = [1, 2, 3, 4]

# Removendo o segundo elemento
numeros.pop(1)  # Agora numeros é [1, 3, 4]

# Removendo o elemento 3
numeros.remove(3)  # Agora numeros é [1, 4]
```

## Ordenando uma lista

É possível ordenar os elementos de uma lista utilizando os métodos `sort()` ou `sorted()`. O método `sort()` ordena a lista permanentemente, enquanto o método `sorted()` retorna uma nova lista ordenada temporariamente. Veja como usar:

```python
numeros = [5, 3, 1, 4, 2]

# Ordenando a lista permanentemente
numeros.sort()  # Agora numeros é [1, 2, 3, 4, 5]

# Ordenando a lista temporariamente
ordenados = sorted(numeros)  # Ordenados é [1, 2, 3, 4, 5]
```

## Fatiando uma lista

Podemos fatiar uma lista para obter uma parte dela. Isso é feito especificando um intervalo de índices utilizando a sintaxe `[inicio:fim]`. Veja como funciona:

```python
numeros = [1, 2, 3, 4, 5]

# Obtendo os três primeiros elementos
primeiros = numeros[:3]  # Retorna [1, 2, 3]

# Obtendo os três últimos elementos
ultimos = numeros[2:]  # Retorna [3, 4, 5]
```

## Exercícios práticos

Agora é hora de praticar o que aprendemos! Aqui estão alguns exercícios para você fazer como homework:

1. Escreva um programa Python que crie uma lista de números pares de 0 a 10 e imprima-a na tela.
2. Escreva um programa que peça ao usuário para digitar três nomes e os adicione a uma lista. Em seguida, ordene a lista em ordem alfabética e imprima-a.
3. Escreva um programa que remova o segundo elemento de uma lista e imprima-a na tela.
4. Escreva um programa que receba uma lista de números e retorne uma nova lista com apenas os números pares.
5. Escreva um programa que pergunte ao usuário quantos números ele deseja adicionar a uma lista e, em seguida, peça para ele digitar esses números. Depois, ordene a lista em ordem crescente e imprima-a.
6. Escreva um programa que receba uma lista de palavras e imprima uma lista contendo o comprimento de cada palavra.
7. Escreva um programa que pergunte ao usuário para digitar uma lista de números e, em seguida, remova todos os números repetidos e imprima a lista resultante.

Lembre-se de praticar esses exercícios para fortalecer seu conhecimento sobre listas em Python. Se tiver alguma dúvida, não hesite em perguntar!
