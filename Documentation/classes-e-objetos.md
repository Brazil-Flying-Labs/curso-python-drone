## Encontro 8 - Classes e Objetos em Python

Bem-vindo ao mais um capítulo da nossa jornada na programação com Python! Neste capítulo, vamos mergulhar no fascinante mundo da Programação Orientada a Objetos (POO) e aprender sobre Classes e Objetos.

A Programação Orientada a Objetos é um paradigma de programação poderoso que nos permite organizar nosso código de forma mais eficiente, criando estruturas de dados chamadas de "Classes" que representam objetos do mundo real. Em POO, os objetos possuem características (atributos) e comportamentos (métodos), tornando o código mais modular e reutilizável.

### Fundamentos da POO

A POO é um paradigma de programação que se concentra em organizar o código em torno de objetos, em vez de apenas funções e lógica. Isso permite uma abordagem mais modular e orientada a objetos para o desenvolvimento de software.

Em POO, um "objeto" é uma instância de uma "classe". Uma classe é como um modelo ou planta baixa para criar objetos. Ela define os atributos (dados) e métodos (funcionalidades) que os objetos dessa classe terão. Por exemplo, podemos ter uma classe `Carro` que define atributos como `marca`, `modelo` e `ano`, e métodos como `ligar` e `desligar`.

Ao criar objetos a partir de uma classe, estamos "instanciando" essa classe. Cada objeto tem seus próprios dados (atributos) e pode executar as funcionalidades definidas na classe (métodos).

A POO ajuda a organizar melhor o código, tornando-o mais modular, reutilizável e fácil de entender e manter. Ela promove o encapsulamento, onde os dados e funcionalidades relacionadas são agrupados em uma única unidade (o objeto), e a herança, onde as classes podem herdar atributos e métodos de outras classes, promovendo a reutilização de código.

### Definindo Classes e Instanciando Objetos

Vamos começar definindo nossas próprias classes em Python. Uma classe é como um modelo para criar objetos. Ela define os atributos (dados) e métodos (funcionalidades) que os objetos dessa classe terão.

```python
class Carro:
    def __init__(self, marca, modelo, ano):
        self.marca = marca
        self.modelo = modelo
        self.ano = ano

    def descrever(self):
        return f"{self.marca} {self.modelo} {self.ano}"
```

Este trecho de código define uma classe chamada `Carro`. Dentro dessa classe, há dois métodos: `__init__` e `descrever`.

O método `__init__` é um método especial em Python chamado de construtor. Ele é executado automaticamente toda vez que um novo objeto da classe é criado. Nesse exemplo, este método recebe parâmetros como `marca`, `modelo` e `ano`, que são atributos do objeto. Dentro do método, esses parâmetros são atribuídos aos atributos do objeto usando a sintaxe `self.nome_do_atributo = valor`.

No contexto de uma classe em Python, `self` é uma referência ao próprio objeto sendo manipulado. Quando um método é chamado em um objeto, o Python automaticamente passa uma referência ao objeto como o primeiro argumento para o método. Por convenção, essa referência é chamada de `self`.

Dentro dos métodos da classe, `self` é usado para acessar e modificar os atributos e métodos desse objeto específico. Por exemplo, em `self.marca = marca` dentro do método `__init__`, estamos atribuindo o valor do parâmetro `marca` ao atributo `marca` do objeto atual.

Usar `self` permite que os métodos da classe saibam a qual objeto eles pertencem e acessem seus atributos e métodos corretamente. Isso é fundamental para a orientação a objetos em Python e é uma prática comum em muitas outras linguagens de programação orientadas a objetos.

O método `descrever` é um método regular da classe que retorna uma string formatada contendo a marca, modelo e ano do carro. Ele utiliza os valores dos atributos do objeto para construir essa string e a retorna usando a expressão de formatação f-string.

Agora que temos nossa classe `Carro`, podemos criar objetos a partir dela, também conhecidos como instâncias:

```python
# Criando instâncias da classe Carro
carro1 = Carro("Ford", "Fusion", 2019)
carro2 = Carro("Toyota", "Corolla", 2020)

# Exibindo as descrições dos carros
print(carro1.descrever())  # Saída: Ford Fusion 2019
print(carro2.descrever())  # Saída: Toyota Corolla 2020
```

Neste exemplo, criamos duas instâncias da classe Carro, carro1 e carro2, passando valores diferentes para os parâmetros marca, modelo e ano. Cada instância tem sua própria cópia dos atributos marca, modelo e ano, ou seja, elas são completamente independentes uma da outra.

Quando chamamos o método descrever() em cada instância, o Python passa automaticamente uma referência ao próprio objeto como o primeiro argumento para o método (ou seja, self). Isso permite que o método acesse os atributos específicos daquela instância, garantindo que cada chamada do método retorne a descrição correta do carro específico.

Essa capacidade de criar cópias separadas dos atributos para cada instancia da classe (objetos), independentes e únicas abre um mundo de possibilidades emocionantes na programação. Você pode criar objetos que representam pessoas, animais, veículos, edifícios - praticamente qualquer coisa que você possa imaginar. E então, você pode interagir com esses objetos, manipulá-los e explorar as diferentes histórias que cada um tem para contar.

### Definindo Métodos

Métodos são funções dentro de uma classe que podem acessar e manipular os dados particulares daquele objeto. Vamos adicionar um método à nossa classe `Carro` para ligar o motor:

```python
class Carro:
    def __init__(self, marca, modelo, ano):
        self.marca = marca
        self.modelo = modelo
        self.ano = ano
        self.ligado = False # Inicialmente, o carro está desligado

    def descrever(self):
        return f"{self.marca} {self.modelo} {self.ano}"

    def ligar(self):
        self.ligado = True
        return "O motor foi ligado."

# Criar um objeto Carro
meu_carro = Carro("Ford", "Fusion", 2019)
print(meu_carro.ligar())  # Saída: O motor foi ligado.
```

Neste trecho de código, estamos criando uma representação da funcionalidade de ligar o motor de um carro em Python. Primeiramente, definimos um método chamado `ligar()` dentro da classe `Carro`. Dentro deste método, temos uma linha que atribui o valor `True` ao atributo `ligado` do próprio objeto, indicando que o motor foi ligado com sucesso. 

É importante notar que utilizamos o parâmetro `self` dentro da definição do método para nos referirmos ao objeto atual. Assim, `self.ligado` significa que estamos acessando o atributo `ligado` do objeto em questão. 

Após a alteração do estado do atributo, o método retorna uma mensagem informando que o motor foi ligado. 

Posteriormente, criamos uma instância da classe `Carro` chamada `meu_carro`, representando um carro da marca Ford, modelo Fusion e ano 2019. 

Por fim, chamamos o método `ligar()` no objeto `meu_carro`, indicando que queremos ligar o motor deste carro específico. Ao imprimir o resultado, a mensagem "O motor foi ligado." será exibida na tela, confirmando que a operação foi bem-sucedida.

Este exemplo demonstra como os métodos de uma classe podem ser utilizados para realizar ações específicas em objetos individuais, encapsulando o comportamento relacionado a esses objetos dentro da própria classe. Isso proporciona um código mais organizado e modular, facilitando a manutenção e a compreensão do programa como um todo.

Vamos criar um método mais interessante e útil para a classe `Carro` que simula a aceleração. Aqui está o exemplo de código:

```python
class Carro:
    def __init__(self, marca, modelo, ano):
        self.marca = marca
        self.modelo = modelo
        self.ano = ano
        self.ligado = False
        self.velocidade = 0 # Inicialmente, o carro está parado

    def descrever(self):
        return f"{self.marca} {self.modelo} {self.ano}"

    def ligar(self):
        self.ligado = True
        return "O motor foi ligado."

    def acelerar(self, incremento):
        if self.velocidade + incremento <= 200:  # Limite de velocidade de 200 km/h
            self.velocidade += incremento
            return f"O carro acelerou para {self.velocidade} km/h."
        else:
            return "Limite de velocidade excedido. Reduza a velocidade."

# Criar um objeto Carro
meu_carro = Carro("Ford", "Fusion", 2019)

# Ligar o motor do carro
print(meu_carro.ligar())  # Saída: O motor foi ligado.

# Acelerar o carro
print(meu_carro.acelerar(50))  # Saída: O carro acelerou para 50 km/h.
print(meu_carro.acelerar(80))  # Saída: O carro acelerou para 130 km/h.
print(meu_carro.acelerar(100)) # Saída: Limite de velocidade excedido. Reduza a velocidade.
```

Neste exemplo, adicionamos um novo método chamado `acelerar()` à classe `Carro`. Este método recebe um argumento `incremento` que representa o aumento na velocidade do carro em quilômetros por hora (km/h). 

Note que dentro do construtor __init__() da classe Carro, foi adicionado um novo atributo chamado velocidade. Este atributo é inicializado com o valor 0 quando um novo objeto da classe Carro é criado. Isso significa que, sempre que instanciamos um novo carro, ele é criado com uma velocidade inicial igual a zero, indicando que o carro está parado. 

Dentro do método `acelerar()`, verificamos se a velocidade atual do carro somada ao incremento não excede o limite de velocidade de 200 km/h. Se não exceder, incrementamos a velocidade atual do carro e retornamos uma mensagem indicando a nova velocidade do carro. Caso contrário, se o limite de velocidade for excedido, retornamos uma mensagem alertando o usuário para reduzir a velocidade.

Ao criar uma instância da classe `Carro` chamada `meu_carro`, ligamos o motor do carro chamando o método `ligar()`. Em seguida, usamos o método `acelerar()` para aumentar a velocidade do carro em diferentes incrementos e imprimimos o resultado na tela.

Este exemplo demonstra como podemos adicionar funcionalidades dinâmicas e interativas à nossa classe `Carro`, permitindo que os objetos da classe simulem comportamentos realistas de um carro em movimento.

### Faça aogra mesmo !

#### Exercício 8.1:

Crie uma classe `Animal` com atributos `nome` e `idade`. Em seguida, crie um objeto dessa classe e imprima suas informações.

#### Exercício 8.2:

Adicione um método `fazer_som` à classe `Animal` que imprima um som característico do animal.

#### Exercício 8.3:

Crie uma classe `Circulo` com um atributo `raio` e métodos para calcular a área e o perímetro do círculo. Em seguida, crie um objeto dessa classe e imprima essas informações.

Lembre-se das seguintes fórmulas:

Claro! Aqui está o texto formatado para Markdown, adequado para uso em arquivos `.md` do Git:

---

## Fórmulas para Calcular Área e Perímetro de um Círculo

A área de um círculo é dada pela fórmula:
   
   ```
   A = π × raio^2
   ```
   
   Onde:
   - \( A \) é a área do círculo,
   - \( π \) é uma constante matemática aproximadamente igual a 3,14159,
   - \( raio \) é o comprimento do raio do círculo.

Essa fórmula é derivada do conceito de que a área de um círculo é proporcional ao quadrado do raio. Multiplicando o quadrado do raio pelo valor de \( π \), obtemos a área do círculo.

O perímetro de um círculo, também chamado de circunferência, é dado pela fórmula:
   
   ```
   P = 2 × π × raio
   ```
   
   Onde:
   - \( P \) é o perímetro do círculo,
   - \( π \) é novamente a constante matemática pi,
   - \( raio \) é o comprimento do raio do círculo.

Essa fórmula representa o comprimento da linha que forma a borda do círculo, ou seja, a circunferência. Multiplicando o valor de \( π \) pelo diâmetro do círculo (que é o dobro do raio), obtemos o perímetro.






### Biblioteca Padrão de Python: Classes Úteis
Além de criar nossas próprias classes, Python também oferece uma vasta biblioteca padrão com classes úteis prontas para uso. Exploraremos algumas das classes principais dessa biblioteca, como `datetime`, `math` e `random`, e aprenderemos como importá-las em nossos programas para realizar tarefas específicas.

Prepare-se para mergulhar de cabeça na Programação Orientada a Objetos e expandir suas habilidades de programação com Python! Pratique bastante, faça perguntas e não tenha medo de errar - é assim que aprendemos melhor. Vamos lá!
