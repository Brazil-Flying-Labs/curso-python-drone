## Encontro 7 - Funções em Python

Neste capítulo, vamos explorar detalhadamente as funções em Python, uma das características mais poderosas da linguagem. As funções permitem organizar o código em blocos reutilizáveis, facilitando a manutenção e a modularidade do seu programa. Abordaremos como criar funções, passar argumentos para elas, armazená-las em módulos e importá-las de diferentes formas.

### Criando uma Função em Python

Em Python, uma função é definida usando a palavra-chave `def`, seguida pelo nome da função e seus parâmetros entre parênteses. O corpo da função é então indentado. 

Vejamos um exemplo simples:

```python
def saudacao(nome):
    """Esta função imprime uma saudação com o nome fornecido."""
    print("Olá, " + nome + "!")
```

Neste exemplo, definimos uma função chamada `saudacao` que recebe um parâmetro `nome`. A docstring, que é uma string entre três aspas duplas, fornece uma descrição da função. Dentro do corpo da função, usamos a função `print()` para exibir uma mensagem de saudação personalizada com o nome fornecido.

Para chamar essa função, usamos seu nome seguido pelos argumentos entre parênteses:

```python
saudacao("João")
```

Isso produzirá a saída: `Olá, João!`.

### Valores de Retorno da Função

Além de realizar tarefas, as funções podem retornar valores usando a palavra-chave `return`. 

Por exemplo:

```python
def soma(a, b):
    """Esta função retorna a soma de dois números."""
    return a + b
```

Nesta função `soma`, definimos dois parâmetros, `a` e `b`, e retornamos a soma desses dois números usando a expressão `return a + b`.

Ao chamar esta função, obteremos o valor da soma dos dois argumentos:

```python
resultado = soma(5, 3)
print(resultado)  # Saída: 8
```

### Passando Argumentos para Funções

Em Python, existem várias maneiras de passar argumentos para uma função: argumentos posicionais, argumentos de palavra-chave e argumentos padrão.

#### Argumentos Posicionais

Os argumentos posicionais são fundamentais em Python, pois são passados para uma função na mesma ordem em que foram definidos na própria função. Isso significa que a primeira variável que você passa será atribuída ao primeiro parâmetro da função, a segunda variável será atribuída ao segundo parâmetro e assim por diante, seguindo a sequência definida na declaração da função.

Por exemplo, considere uma função simples que concatena duas strings:

```python
def concatenar_strings(string1, string2):
    """Esta função concatena duas strings."""
    return string1 + string2
```

Ao chamar essa função e passar argumentos posicionais, a primeira string que você passa será atribuída à variável `string1` e a segunda string será atribuída à variável `string2`, na ordem em que foram passadas:

```python
resultado = concatenar_strings("Olá, ", "mundo!")
print(resultado)  # Saída: Olá, mundo!
```

Neste exemplo, a string "Olá, " é atribuída a `string1` e a string "mundo!" é atribuída a `string2`, resultando na concatenação das duas strings e na saída "Olá, mundo!".

É importante entender que a ordem dos argumentos posicionais ao chamar uma função deve corresponder à ordem dos parâmetros na definição da função. Caso contrário, os valores serão atribuídos aos parâmetros de forma incorreta, o que pode levar a resultados inesperados ou a erros de execução no seu código.

Portanto, ao utilizar argumentos posicionais em Python, certifique-se sempre de passá-los para a função na ordem correta, de acordo com a definição dos parâmetros na própria função. Isso garantirá o funcionamento correto e previsível do seu código.

#### Argumentos Nomeados

Com os argumentos nomeados em Python, você ganha uma flexibilidade adicional ao chamar uma função. Em vez de depender da ordem em que os parâmetros foram definidos na função, você pode especificar diretamente o nome do parâmetro ao passar o argumento, tornando o código mais claro e menos propenso a erros.

Por exemplo, considere uma função que recebe dois argumentos e os concatena:

```python
def concatenar_strings(string1, string2):
    """Esta função concatena duas strings."""
    return string1 + string2
```

Com argumentos nomeados, você pode passar os argumentos na ordem que desejar, especificando os nomes dos parâmetros:

```python
resultado = concatenar_strings(string1="Olá, ", string2="mundo!")
print(resultado)  # Saída: Olá, mundo!
```

Neste exemplo, passamos explicitamente os argumentos usando os nomes dos parâmetros, o que torna mais claro o propósito de cada argumento. Isso também permite que você altere a ordem dos argumentos ou omita alguns deles, se necessário, sem se preocupar com a ordem definida na função. Por exemplo:

```python
resultado = concatenar_strings(string2="mundo!", string1="Olá, ")
print(resultado)  # Saída: Olá, mundo!
```

Neste caso, invertendo a ordem dos argumentos nomeados, ainda obtemos o mesmo resultado.

#### Argumentos Padrão

Ao definir valores padrão para os parâmetros de uma função em Python, você fornece um valor inicial que será usado automaticamente caso o argumento correspondente não seja fornecido durante a chamada da função. Isso oferece uma maneira conveniente de criar funções com comportamento predefinido.

Vejamos um exemplo para ilustrar esse conceito:

```python
def saudacao(nome="Mundo"):
    """Esta função imprime uma saudação com o nome fornecido, ou "Mundo" se nenhum nome for fornecido."""
    print("Olá, " + nome + "!")
```

Neste exemplo, definimos uma função chamada `saudacao` que possui um parâmetro `nome` com um valor padrão de `"Mundo"`. Se nenhum argumento for fornecido quando a função for chamada, o valor padrão será usado automaticamente:

```python
saudacao()  # Saída: Olá, Mundo!
```

No entanto, se um argumento for fornecido, ele substituirá o valor padrão:

```python
saudacao("João")  # Saída: Olá, João!
```

Além disso, a capacidade de definir valores padrão para os parâmetros de uma função simplifica a chamada da função, pois nem sempre é necessário fornecer todos os argumentos ao chamá-la. Isso pode tornar o código mais legível e reduzir a quantidade de código redundante.

### Faça agora mesmo !

#### Exercício 7.1: 

Neste exercício, você será desafiado a criar uma função em Python chamada `calcular_area_retangulo`. Esta função terá a importante tarefa de calcular a área de um retângulo com base e altura fornecidas como argumentos.

Para isso, você precisará lembrar que a fórmula para calcular a área de um retângulo é simplesmente multiplicar a base pela altura. Portanto, sua função deve seguir essa lógica para retornar o valor correto da área.

Ao criar a função, você deve definir dois parâmetros: `base` e `altura`, que representarão as dimensões do retângulo. Dentro da função, você irá multiplicar esses dois valores para obter a área total do retângulo.

Uma vez que a função esteja definida, você pode testá-la com diferentes valores de base e altura para garantir que esteja funcionando corretamente. Lembre-se de que a função deve ser capaz de lidar com números inteiros ou decimais, então teste-a com uma variedade de valores para garantir sua robustez.

### Passando uma Lista como Argumento

Em Python, você pode passar não apenas valores individuais, mas também estruturas de dados complexas, como listas, como argumentos para uma função. Isso oferece uma grande flexibilidade, permitindo que você trabalhe com conjuntos de dados arbitrariamente grandes e dinâmicos dentro das suas funções.

Por exemplo:

```python
def listar_nomes(nomes):
    """Esta função imprime os nomes da lista fornecida."""
    for nome in nomes:
        print(nome)

nomes = ["Maria", "João", "Ana"]
listar_nomes(nomes)
```

Neste exemplo, passamos a lista `nomes` como argumento para a função `listar_nomes`. Dentro da função, iteramos sobre cada elemento da lista e o imprimimos.

Quando você passa uma lista como argumento para uma função, a função recebe uma referência para a lista original, o que significa que qualquer alteração feita na lista dentro da função afetará diretamente a lista original fora da função. Isso é possível porque as listas em Python são objetos mutáveis.

Vamos ver um exemplo para entender melhor:

```python
def dobrar_elementos(lista):
    """Esta função dobra cada elemento da lista fornecida."""
    for i in range(len(lista)):
        lista[i] *= 2

numeros = [1, 2, 3, 4, 5]
dobrar_elementos(numeros)
print(numeros)  # Saída: [2, 4, 6, 8, 10]
```

Neste exemplo, definimos uma função chamada `dobrar_elementos` que recebe uma lista como argumento. Dentro da função, multiplicamos cada elemento da lista por 2. Ao chamar a função com a lista `numeros`, a lista é modificada diretamente pela função, e essas alterações são refletidas quando imprimimos a lista fora da função.

É importante ter em mente que, ao passar uma lista como argumento, a função não cria uma cópia da lista. Em vez disso, ela trabalha com a própria lista original. Portanto, qualquer modificação feita na lista dentro da função afetará a lista original fora da função.

Note também que o nome do parâmetro na definição da função não precisa ser o mesmo que o nome da lista passada como argumento. 

### Faça agora mesmo !

#### Exercício 7.2: 

Imagine que você é um programador e está desenvolvendo um software para ajudar os alunos a calcular suas médias em diferentes disciplinas. Sua tarefa é criar uma função em Python chamada `calcular_media` que aceita uma lista de notas como entrada e retorna a média dessas notas.

Você pode começar definindo a estrutura da função e, em seguida, implementar o código dentro dela para calcular a média das notas.

Lembre-se de que a função deve ser capaz de lidar com qualquer quantidade de notas, então certifique-se de testá-la com diferentes números de notas.

Aqui estão algumas dicas que podem ajudar nesse exercício:

**sum():** A função `sum()` pode ser usada para somar todos os elementos de uma lista. Isso será útil para calcular a soma total das notas.

**len():** A função `len()` retorna o número de elementos em uma lista. Você pode usá-la para contar quantas notas foram dadas, o que será necessário para calcular a média.

**Operadores aritméticos:** Você precisará usar operadores aritméticos básicos, como adição (+) e divisão (/), para calcular a média das notas.

Depois de criar a função, teste-a com diferentes conjuntos de notas para garantir que esteja funcionando corretamente. Por exemplo, você pode usar as notas de um aluno em diferentes disciplinas e verificar se a função retorna a média correta.

### Armazenando Funções em Módulos

Para organizar suas funções em arquivos separados, você pode armazená-las em módulos. Um módulo é simplesmente um arquivo Python contendo definições e declarações.

Por exemplo, suponha que tenhamos um arquivo chamado `operacoes.py` com a seguinte função:

```python
# operacoes.py
def quadrado(x):
    """Esta função retorna o quadrado do número fornecido."""
    return x ** 2
```

Para utilizar esta função em nosso programa principal, precisamos importá-la:

```python
# main.py
import operacoes

resultado = operacoes.quadrado(5)
print(resultado)  # Saída: 25
```

Quando importamos um módulo inteiro usando a sintaxe `import nome_do_modulo`, todas as funções e variáveis definidas nesse módulo ficam disponíveis para uso, mas precisamos especificar o nome do módulo seguido de um ponto (.) para acessá-las.

No exemplo acima, importamos o módulo `operacoes`. Para chamar a função `quadrado()` que está dentro deste módulo, usamos o nome do módulo seguido de um ponto `operacoes.` para indicar que estamos acessando uma função dentro do módulo `operacoes`.

Essa abordagem é útil quando estamos importando módulos que contêm muitas funções e queremos evitar possíveis conflitos de nomes entre as funções do módulo importado e as funções do nosso programa principal. Ao usar o nome do módulo seguido de um ponto, deixamos claro de onde vem a função que estamos chamando.

### Importando de Módulos e Funções

Além de importar um módulo inteiro, você pode importar funções específicas usando a sintaxe `from ... import ...`. 

Por exemplo:

```python
# main.py
from operacoes import quadrado

resultado = quadrado(5)
print(resultado)  # Saída: 25
```

Ao usar a sintaxe `from ... import ...`, podemos importar funções específicas de um módulo, em vez de importar o módulo inteiro.

Ao importar apenas as funções necessárias, tornamos nosso código mais conciso e claro. Isso facilita a leitura e compreensão do código por outras pessoas que possam estar revisando ou mantendo-o.

Além disso, importar apenas as funções necessárias pode melhorar o desempenho do programa, especialmente em casos onde o módulo importado é grande e contém muitas funções que não são utilizadas. Isso ocorre porque o interpretador Python não precisa carregar todo o conteúdo do módulo, apenas as funções importadas são carregadas na memória.

Você também pode renomear funções ao importá-las:

```python
# main.py
from operacoes import quadrado as quad

resultado = quad(5)
print(resultado)  # Saída: 25
```

Renomear funções ao importar oferece flexibilidade e clareza ao código. Essa prática é especialmente útil como mais uma forma de evitar conflitos de nomes entre as funções importadas e as funções já definidas em seu código.

### Faça agora mesmo !

#### Exercício 7.3: 

Neste exercício, você vai organizar as funções criadas nos exercícios 7.1 e 7.2 em um módulo Python chamado `minhas_funcoes.py`. Depois, você vai importar as duas funções desse módulo e criar um código para chamá-las.

Para começar, copie as funções que você desenvolveu nos exercícios 7.1 e 7.2 para um arquivo Python chamado `minhas_funcoes.py`. Certifique-se de que cada função esteja definida corretamente no arquivo.

Depois de organizar as funções em um módulo, você vai importar essas funções em `main.py`. Utilize a sintaxe `from minhas_funcoes import nome_da_funcao` para importar cada função individualmente.

Por fim, escreva um código que chama ambas as funções importadas, passando os argumentos necessários.

Com isso, você estará organizando suas funções em um módulo e aprendendo a importá-las e utilizá-las em um código Python separado. Isso facilitará a reutilização das suas funções em diferentes partes do seu projeto!

### Curiosidade: Alan Turing, o Gênio por Trás da Quebra do Código Enigma

Alan Turing, nascido em 23 de junho de 1912 na Inglaterra, foi um renomado matemático, cientista da computação e pioneiro em inteligência artificial. Sua contribuição mais conhecida foi sua liderança na quebra do código Enigma durante a Segunda Guerra Mundial, um feito que teve um impacto significativo no resultado da guerra.

Durante o conflito, os alemães usavam a máquina de codificação Enigma para enviar mensagens secretas. Essas mensagens eram extremamente difíceis de decifrar devido à complexidade do código gerado pela Enigma. No entanto, Turing liderou um esforço para desenvolver uma máquina chamada "Bombe", que foi projetada para quebrar o código Enigma.

A Bombe foi baseada em princípios matemáticos e foi uma das primeiras formas de computação eletrônica. Ela funcionava testando diferentes combinações de configurações da máquina Enigma até encontrar aquela que correspondia à mensagem codificada. Este processo de decodificação foi intensivo em computação e exigiu uma quantidade enorme de cálculos.

Graças à máquina Bombe as forças aliadas foram capazes de decifrar uma grande quantidade de mensagens alemãs. Essas informações forneceram uma vantagem crucial, permitindo que as forças aliadas antecipassem os movimentos e planos das forças inimigas.

O trabalho de Turing na quebra do código Enigma foi uma demonstração notável de sua genialidade e habilidade matemática. Além disso, foi um marco importante no desenvolvimento da computação e da criptografia, pavimentando o caminho para futuros avanços tecnológicos.

![A máquina de Turing](/Images/alan-turing-bombe.png "A máquina de Turing")

### Exercícios práticos

Agora é hora de praticar o que aprendemos! Aqui estão alguns exercícios para você fazer para testar seus conhecimentos.

#### Exercício 7.4:

Neste exercício, você vai criar uma função em Python chamada `resumo_sanduiche` que aceita uma lista de ingredientes como argumento. Essa função deve iterar sobre os elementos dessa lista e exibir um resumo do sanduíche criado.

Para começar, defina a função `resumo_sanduiche` com um parâmetro chamado `ingredientes`. Dentro da função, você irá iterar sobre cada ingrediente na lista e acumular esses ingredientes em uma string que representa o resumo do sanduíche.

Por exemplo, se você fornecer uma lista de ingredientes como `["pão", "queijo", "presunto", "alface", "tomate"]`, o resumo do sanduíche deverá ser algo como "Seu sanduíche possui: pão, queijo, presunto, alface e tomate".

Depois de criar a função `resumo_sanduiche`, teste-a com diferentes conjuntos de ingredientes para garantir que esteja funcionando corretamente. 

#### Exercício 7.5:

Neste exercício, você vai criar um jogo de adivinhação em Python. O objetivo do jogo é que o jogador tente adivinhar um número secreto escolhido aleatoriamente pelo computador.

Para começar, você precisará importar o módulo random, que permitirá gerar números aleatórios. Em seguida, crie uma função chamada jogo_adivinhacao que irá conter toda a lógica do jogo.

Dentro da função jogo_adivinhacao, o computador deve gerar um número aleatório entre 1 e 100, que será o número secreto a ser adivinhado pelo jogador. Em seguida, o jogador terá um número limitado de tentativas para adivinhar o número secreto.

Cada vez que o jogador fizer uma tentativa, o programa deve informar se o número é maior, menor ou igual ao número secreto. Além disso, o programa deve contar quantas tentativas o jogador fez e informar isso a ele.

O jogo deve continuar até que o jogador adivinhe corretamente o número secreto ou até que ele use todas as suas tentativas.

Ao final do jogo, o programa deve informar ao jogador se ele ganhou ou perdeu, além de mostrar o número secreto e o número de tentativas que ele utilizou.

#### Exercício 7.6:

Neste exercício, você vai criar um programa em Python que calcula o Índice de Massa Corporal (IMC) de uma pessoa. O IMC é uma medida usada para avaliar se uma pessoa está com peso adequado em relação à sua altura.

Para começar, você pode definir uma função chamada calcular_imc que aceita dois parâmetros: o peso da pessoa em quilogramas e a altura da pessoa em metros. Dentro desta função, você vai utilizar a fórmula do IMC para calcular o valor.

A fórmula do IMC é dada por: IMC = peso / (altura ** 2)

Depois de calcular o IMC, você pode adicionar uma lógica para classificar o resultado em diferentes faixas de peso, como "Abaixo do peso", "Peso normal", "Sobrepeso", "Obesidade Grau I", "Obesidade Grau II" e "Obesidade Grau III".

Aqui estão os intervalos de valores de IMC para cada categoria:

Abaixo do peso: IMC < 18.5
Peso normal: 18.5 <= IMC < 25
Sobrepeso: 25 <= IMC < 30
Obesidade Grau I: 30 <= IMC < 35
Obesidade Grau II: 35 <= IMC < 40
Obesidade Grau III: IMC >= 40

Esses são os valores comumente utilizados para classificar as diferentes faixas de peso com base no IMC. Ao calcular o IMC de uma pessoa, podemos comparar o resultado com esses intervalos para determinar em qual categoria ela se enquadra.

Por fim, o programa deve imprimir o valor do IMC calculado e a classificação correspondente, para que o usuário possa avaliar sua condição física.


