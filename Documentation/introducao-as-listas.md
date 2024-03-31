## Encontro 3 - Introdução às Listas

Hoje vamos explorar um dos conceitos mais importantes da linguagem Python: listas. As listas são estruturas de dados fundamentais que permitem armazenar coleções de elementos de forma ordenada e acessível. Durante esta aula, vamos aprender sobre o que são listas, como adicionar e remover elementos, ordenar uma lista e fatiar uma lista. Além disso, vamos praticar com alguns exercícios práticos para reforçar o que aprendemos.

### O que são listas?

Uma lista em Python é uma coleção ordenada de elementos. Esses elementos podem ser de diferentes tipos, como números, strings, ou até mesmo outras listas. As listas são definidas utilizando colchetes `[]` e os elementos são separados por vírgulas. Vamos ver alguns exemplos:

```python
# Exemplo de lista de números
numeros = [1, 2, 3, 4, 5]

# Exemplo de lista de strings
nomes = ['Alice', 'Bob', 'Carol', 'David']

# Exemplo de lista mista
misturada = [1, 'dois', 3.0, 'quatro']
```

### Acessando os elementos de uma lista

Os elementos de uma lista são acessados utilizando índices. É importante lembrar que os índices em Python começam em 0, não em 1. Veja como acessar os elementos de uma lista:

```python
numeros = [10, 20, 30, 40, 50]

# Acessando o primeiro elemento da lista
primeiro = numeros[0]  # Retorna 10
print(primeiro)  # Retorna 10

# Acessando o terceiro elemento da lista
terceiro = numeros[2]  
print(terceiro)  # Retorna 30
```

Vamos armazenar os nomes de alguns amigos em uma lista e depois exibir esses nomes um de cada vez.

```python
# Criando uma lista de nomes de amigos
amigos = ["João", "Maria", "Pedro", "Ana", "Carlos"]

# Exibindo o nome de cada amigo um de cada vez
print("Nomes dos amigos:")
print(amigos[0])
print(amigos[1])
print(amigos[2])
print(amigos[3])
print(amigos[4])
```

Neste exemplo, criamos uma lista chamada `amigos` contendo os nomes de alguns amigos. Em seguida, acessamos cada elemento da lista individualmente utilizando os índices `[0]`, `[1]`, `[2]`, `[3]` e `[4]`, e imprimimos o nome de cada amigo separadamente. Isso nos permite exibir cada nome individualmente, em linhas separadas.

Podemos também utilizar a lista de amigos criada anteriormente e enviar uma mensagem personalizada para cada um deles.

```python
# Criando uma lista de nomes de amigos
amigos = ["João", "Maria", "Pedro", "Ana", "Carlos"]

# Enviando uma mensagem personalizada para cada amigo
print("Mensagens para os amigos:")
print("Olá, " + amigos[0] + ", espero que você esteja bem.")
print("Oi, " + amigos[1] + "! Tenha um ótimo dia!")
print("Olá, " + amigos[2] + ", como tem passado?")
print("Oi, " + amigos[3] + " estou pensando em você.")
print("Olá, " + amigos[4] + "! Vamos marcar algo em breve?")
```

Neste exemplo, utilizamos a lista amigos contendo os nomes de alguns amigos. Em seguida, acessamos cada elemento da lista individualmente utilizando os índices [0], [1], [2], [3] e [4], e concatenamos as strings utilizando o operador + para enviar uma mensagem personalizada para cada amigo. Isso nos permite enviar uma mensagem personalizada para cada amigo.

### Faça agora mesmo !

#### Exercício 3.1:

Imagine que você adora veículos e está criando uma lista para representar diferentes exemplos de carros ou motos que você gostaria de possuir um dia. Sua tarefa é criar uma lista chamada `veiculos_favoritos` e preenchê-la com vários exemplos de veículos dos quais você gosta.

Instruções:

1. Crie uma lista chamada `veiculos_favoritos` e preencha-a com pelo menos cinco exemplos de carros ou motos que você admira ou gostaria de possuir no futuro.

2. Utilize sua lista para exibir uma série de declarações sobre esses veículos. Por exemplo, "Gostaria de ter um carro da marca Tesla" ou "Adoraria pilotar uma moto da marca Harley-Davidson".

3. Certifique-se de usar frases completas e corretamente formatadas para cada declaração, utilizando a formatação de string adequada para inserir os nomes dos veículos na frase.

Exemplo de Saída:

```
Lista de Veículos Favoritos:
1. Gostaria de ter um carro da marca Tesla.
2. Adoraria pilotar uma moto da marca Harley-Davidson.
3. Sonho em dirigir um carro da marca Ferrari.
4. Meu objetivo é ter uma moto da marca Ducati.
5. Seria incrível ter um carro da marca Lamborghini.
```

Lembre-se de ser criativo ao escolher os veículos para sua lista e divirta-se imaginando as experiências que você gostaria de ter com eles!

### Modificando e adicionando elementos

Podemos modificar os elementos de uma lista atribuindo novos valores a eles. Também podemos adicionar novos elementos utilizando o método `append()` ou inserindo elementos em uma posição específica utilizando o método `insert()`. Veja alguns exemplos:

```python
numeros = [1, 2, 3]

# Modificando o segundo elemento
numeros[1] = 10  
print(numeros)  # Agora numeros é [1, 10, 3]

# Adicionando um novo elemento ao final da lista
numeros.append(4)  
print(numeros)  # Agora numeros é [1, 10, 3, 4]

# Inserindo um novo elemento na segunda posição
numeros.insert(1, 5)  
print(numeros)  # Agora numeros é [1, 5, 10, 3, 4]
```

### Removendo elementos

Para remover elementos de uma lista, podemos utilizar o método `pop()` para remover um elemento específico pelo seu índice, o método `remove()` para remover um elemento pelo seu valor, ou até mesmo o método `pop()` sem argumento para remover o último elemento da lista. Veja como funciona:

```python
poligonos = ["triângulo", 5, "quadrado", "pentágono", "hexágono"]

# Removendo o terceiro elemento utilizando pop()
poligonos.pop(2)  
print(poligonos)  # Agora poligonos é ['triângulo', 5, 'pentágono', 'hexágono']

# Removendo o número inteiro 5 da lista, utilizando remove()
poligonos.remove(5)  
print(poligonos)  # Agora poligonos é ['triângulo', 'pentágono', 'hexágono']

# Removendo o último elemento utilizando pop() sem argumento
elemento_removido = poligonos.pop()  
print(poligonos)  # Agora poligonos é ['triângulo', 'pentágono']
print("Elemento removido: " + elemento_removido)
```

No exemplo fornecido, o comando `poligonos.remove(5)` remove o elemento 5 da lista pelo seu valor, não pelo seu índice. É importante distinguir entre remover um elemento pelo seu valor e remover um elemento pelo seu índice. Se quiséssemos remover o elemento 5 pelo seu índice, deveríamos usar poligonos.pop(1), pois 1 é o índice na lista para o elemento 5.

O método `pop()` sem argumento remove e retorna o último elemento da lista. Isso pode ser útil quando queremos remover o último item de uma lista e não nos importamos com o valor do item removido. 

## Ordenando uma lista

É possível ordenar os elementos de uma lista utilizando os métodos `sort()` ou `sorted()`. O método `sort()` ordena a lista permanentemente em ordem crescente por padrão, enquanto o método `sorted()` retorna uma nova lista ordenada temporariamente. Para ordenar em ordem decrescente, podemos passar o argumento `reverse=True` para ambos os métodos. Veja como usar:

```python
numeros = [5, 3, 1, 4, 2]
print(numeros)  # Lista original [5, 3, 1, 4, 2]

# Ordenando a lista permanentemente em ordem crescente
numeros.sort()  
print(numeros)  # Agora numeros é [1, 2, 3, 4, 5]

# Ordenando a lista permanentemente em ordem decrescente
numeros.sort(reverse=True)  
print(numeros)  # Agora numeros é [5, 4, 3, 2, 1]

# Ordenando a lista temporariamente em ordem crescente
ordenados = sorted(numeros)
print(ordenados)  # Ordenados é [1, 2, 3, 4, 5]
print(numeros)  # A lista numeros continua sendo [5, 4, 3, 2, 1]

# Ordenando a lista temporariamente em ordem decrescente
ordenados_decrescente = sorted(numeros, reverse=True)  
print(ordenados_decrescente)  # ordenados_decrescente é [5, 4, 3, 2, 1]
print(numeros)  # A lista numeros continua sendo [5, 4, 3, 2, 1]
```

### Fatiando uma lista

Podemos fatiar uma lista para obter uma parte dela. Isso é feito especificando um intervalo de índices utilizando a sintaxe `[inicio:fim]`. Veja como funciona:

```python
# Criando uma lista de nomes de pensadores da matemática
pensadores_matematica = ["Euler", "Gauss", "Newton", "Descartes", "Fermat"]

print(pensadores_matematica)  # A lista original é ["Euler", "Gauss", "Newton", "Descartes", "Fermat"]

# Obtendo os três primeiros pensadores
primeiros = pensadores_matematica[:3]  
print(primeiros)  # Retorna ["Euler", "Gauss", "Newton"]
print(pensadores_matematica)  # A lista de pensadores_matematica continua sendo ["Euler", "Gauss", "Newton", "Descartes", "Fermat"]

# Obtendo os três últimos pensadores
ultimos = pensadores_matematica[2:]  
print(ultimos)  # Retorna ["Newton", "Descartes", "Fermat"]
print(pensadores_matematica)  # A lista de pensadores_matematica continua sendo ["Euler", "Gauss", "Newton", "Descartes", "Fermat"]

# Obtendo parte do meio da lista (do segundo até o quarto elemento, inclusive)
meio = pensadores_matematica[1:4]  
print(meio)  # Retorna ["Gauss", "Newton", "Descartes"]
print(pensadores_matematica)  # A lista de pensadores_matematica continua sendo ["Euler", "Gauss", "Newton", "Descartes", "Fermat"]
```

Este código demonstra como utilizar o operador de fatiamento : em listas em Python. Primeiro, uma lista de nomes de pensadores da matemática é criada. Em seguida, diferentes fatias da lista original são criadas e impressas, mostrando como acessar os primeiros três elementos, os últimos três elementos e uma parte do meio da lista. Note que, apesar de criar novas variáveis com as fatias, a lista original permanece inalterada.

Note que quando utilizamos o operador de fatiamento `[:]` em uma lista, o segundo índice após os dois pontos não é incluído no resultado. Por exemplo, ao obter os três primeiros pensadores de uma lista, estamos acessando os elementos com índices 0, 1 e 2 da lista, e não incluímos o índice 3. Da mesma forma, ao pegar uma parte do meio da lista, do segundo até o quarto elemento, inclusive, o último elemento não é incluído no resultado. Isso se deve ao fato de que o operador de fatiamento define um intervalo semiaberto, onde o último elemento especificado não é incluído. Essa convenção é adotada para facilitar a manipulação de intervalos e evitar ambiguidades durante a operação de fatiamento de listas.

### Faça agora mesmo !

#### Exercício 3.2:

Você está organizando um jantar para seus amigos e deseja enviar convites para todos eles. No entanto, sua lista de amigos não está em ordem alfabética e você prefere que os convites sejam enviados nessa ordem. Sua tarefa é criar uma lista de 7 nomes de amigos e, em seguida, ordená-la em ordem alfabética usando o método sort(). Depois de ordenar a lista, imprima-a para garantir que os convites serão enviados na ordem correta.

Certifique-se de que os nomes estejam corretamente ordenados em ordem alfabética ao imprimir a lista final. Isso garantirá que os convites sejam enviados aos seus amigos na ordem desejada.

#### Exercício 3.3:

Você descobriu de última hora que o local alugado para o jantar permite apenas 5 pessoas, e você precisa remover duas pessoas da sua lista de convidados. No entanto, você quer fazer isso sem parecer indelicado. Decidiu-se que a maneira mais justa de fazer isso é remover as últimas pessoas da lista, pela ordem alfabética, ou seja, as duas últimas da lista. Sua tarefa é usar o fatiamento de lista para remover essas duas últimas pessoas da sua lista de amigos e, em seguida, imprimir a lista atualizada para verificar as alterações.

#### Exercício 3.4:

Apesar de todos os preparativos, um de seus amigos avisou de última hora que não conseguirá comparecer ao jantar. Você precisa remover esse amigo da lista e inserir outra pessoa na posição correta na lista em ordem alfabética, para evitar a necessidade de reordenar a lista inteira. Sua tarefa é usar métodos de manipulação de lista para realizar essa operação e, em seguida, imprimir a lista atualizada para verificar as alterações.

### Curiosidade: **Isaac Newton, o Gênio que Moldou o Mundo Moderno**

Isaac Newton, nascido em 1642 na Inglaterra, é reconhecido como um dos maiores cientistas de todos os tempos. Sua obra revolucionária abrange desde a física até a matemática e a astronomia, deixando um legado que moldou o mundo moderno de maneiras profundas e duradouras.

Uma das contribuições mais notáveis de Newton foi sua formulação das três leis do movimento, que estabeleceram os fundamentos da mecânica clássica. Essas leis descrevem como os objetos se movem sob a influência de forças, fornecendo uma estrutura precisa para entender o comportamento dos corpos em movimento. Elas são a base de inúmeras tecnologias e aplicações práticas em nosso mundo atual.

Além disso, Newton desenvolveu a teoria da gravitação universal, uma ideia revolucionária que explicava como os corpos se atraem mutuamente com uma força proporcional às suas massas e inversamente proporcional ao quadrado da distância entre eles. Esta teoria não apenas explicou os movimentos dos corpos celestes, como planetas e estrelas, mas também permitiu prever com precisão os movimentos dos objetos em nosso próprio planeta. 

Hoje, as contribuições de Newton estão presentes em praticamente todas as esferas de nossa vida cotidiana. Desde a tecnologia espacial, onde suas leis são fundamentais para o design e operação de satélites que impulsionam a comunicação global e a navegação, até o campo da engenharia, onde são aplicadas em projetos de construção e transporte. 

Além disso, as leis de Newton são essenciais para entender fenômenos naturais como o movimento dos corpos na água, o voo de aviões e até mesmo a maneira como os esportes são jogados e os brinquedos funcionam. Em essência, o trabalho de Isaac Newton é um testemunho da poderosa interseção entre a ciência fundamental e a tecnologia aplicada, demonstrando como a compreensão profunda dos princípios naturais pode impulsionar inovações que transformam o mundo.

### Exercícios práticos

Agora é hora de praticar o que aprendemos! Aqui estão alguns exercícios para você fazer para testar seus conhecimentos.

#### Exercício 3.5:
Escreva um programa Python que crie uma lista chamada "frutas" contendo os seguintes elementos: "maçã", "banana", "laranja", "uva" e "abacaxi". Em seguida, imprima a lista na tela. 

#### Exercício 3.6:
Modifique o programa anterior para adicionar uma fruta à lista e também remova uma fruta existente. Após cada operação, imprima a lista atualizada na tela.
 
#### Exercício 3.7:
Crie uma lista de números inteiros aleatórios. Em seguida, ordene a lista em ordem crescente e imprima-a. Depois, fatie a lista para imprimir apenas os três primeiros elementos e os três últimos elementos.

#### Exercício 3.8:
Escreva um programa que peça ao usuário para digitar três nomes e os adicione a uma lista. Em seguida, ordene a lista em ordem alfabética e imprima-a.

#### Exercício 3.9:
Escreva um programa que crie uma lista com cinco palavras e imprima o comprimento de cada palavra.

Lembre-se de praticar esses exercícios para fortalecer seu conhecimento sobre listas em Python. Se tiver alguma dúvida, não hesite em perguntar!
