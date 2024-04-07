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

### Faça agora mesmo !

#### Exercício 8.1:

Crie uma classe `Animal` com atributos `nome` e `idade`. Em seguida, crie um objeto dessa classe e imprima suas informações.

#### Exercício 8.2:

Adicione um método `fazer_som` à classe `Animal` que imprima um som característico do animal.

#### Exercício 8.3:

Crie uma classe `Circulo` com um atributo `raio` e métodos para calcular a área e o perímetro do círculo. Em seguida, crie um objeto dessa classe e imprima essas informações.

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

### Herança em Programação Orientada a Objetos

A herança é um dos conceitos fundamentais da Programação Orientada a Objetos (POO). Ela permite que uma classe, chamada de classe derivada ou subclasse, herde atributos e métodos de outra classe, chamada de classe base ou superclasse.

Em termos simples, podemos pensar na herança como uma relação "é-um". Por exemplo, se tivermos uma classe `Animal` e uma classe `Cachorro`, podemos dizer que um cachorro "é-um" animal. Portanto, faz sentido que a classe `Cachorro` herde características da classe `Animal`, como métodos para se locomover, comer, dormir, etc.

A herança proporciona uma forma de reutilização de código, já que as subclasses podem aproveitar o comportamento e as características da classe base sem precisar reescrever o código. Além disso, ela permite a extensão e especialização das classes, adicionando novos atributos e métodos ou alterando os existentes conforme necessário.

A herança é uma poderosa ferramenta na POO que nos permite criar hierarquias de classes e organizar o código de forma mais eficiente e modular, promovendo a reutilização, a extensibilidade e a flexibilidade do software.

### Carro Elétrico 

Vamos ver esse conceito na prática com o exemplo de um carro elétrico. Primeiro, utilizaremos a classe `Carro` como a classe base. Essa classe contém atributos comuns a todos os carros, como marca, modelo e ano. Em seguida, criaremos uma classe derivada chamada `CarroEletrico`, que herda da classe `Carro`. Esta nova classe terá funcionalidades específicas para carros elétricos, como a capacidade da bateria e métodos para carregar a bateria e mostrar a carga atual.

```python
class Carro:
    --snip--

class CarroEletrico(Carro):
    def __init__(self, marca, modelo, ano, capacidade_bateria):
        super().__init__(marca, modelo, ano)
        self.capacidade_bateria = capacidade_bateria
        self.carga_bateria = 0.3 * capacidade_bateria  # Inicialmente a bateria está 30% carregada

    def carregar(self, carga):
        self.carga_bateria += carga
        return "Carregando a bateria do carro elétrico."

    def mostrar_carga_bateria(self):
        percentual_bateria = (self.carga_bateria / self.capacidade_bateria) * 100
        return f"Carga da bateria: {self.carga_bateria:.1f} kWh ({percentual_bateria:.1f}%)."

# Vamos criar um objeto Carro Elétrico
tesla = CarroEletrico("Tesla", "Model S", 2022, 75)
print(tesla.ligar())  # Saída: O motor foi ligado.
print(tesla.acelerar(50))  # Saída: Acelerando o carro.
print(tesla.mostrar_carga_bateria())  # Saída: Carga da bateria: 22.5 kWh (30.0%)

# Agora vamos carregar esse carro!
meu_carro_eletrico.carregar(20)  # Carregando mais 20 kWh na bateria
print(meu_carro_eletrico.mostrar_carga_bateria())  # Saída: Carga da bateria: 42.5 kWh (56.7%)
```

Neste exemplo criamos a classe `CarroEletrico`, que herda da classe `Carro`. Isso significa que a classe `CarroEletrico` possui todos os atributos e métodos da classe `Carro`, além de seus próprios atributos e métodos específicos para carros elétricos. Na programação orientada a objetos, quando uma classe herda de outra classe, ela adquire todos os métodos e atributos da classe base. Isso significa que, se uma classe derivada não definir um método que está presente na classe base, ela ainda pode acessá-lo e usá-lo.

Na inicialização da classe `CarroEletrico`, definimos um atributo adicional `capacidade_bateria` e adicionamos outro atributo `carga_bateria` com 30% da capacidade total da bateria. A seguir, implementamos dois métodos específicos: `carregar()` para adicionar carga à bateria e `mostrar_carga_bateria()` para exibir a carga atual da bateria em kWh e em percentual.

Depois criamos um objeto `testa` a partir da classe `CarroEletrico`, que representa um carro elétrico da marca Tesla, modelo Model S, fabricado no ano de 2022 e com capacidade de bateria de 75 kWh. 

Após criar o objeto `tesla`, chamamos o método `ligar()`, que está definido na classe `Carro`. Esse método simula o ato de ligar o motor do carro elétrico, definindo o atributo `ligado` como `True`. A saída dessa chamada é a mensagem "O motor foi ligado.".

Note que a classe `Carro` possui o método `ligar()`, que simula o ato de ligar o motor do carro. Quando criamos um objeto da classe `CarroEletrico` e chamamos o método `ligar()`, mesmo que esse método não tenha sido explicitamente definido na classe `CarroEletrico`, ele está presente na classe pai, `Carro`. Portanto, o objeto da classe `CarroEletrico` pode acessar e usar o método `ligar()` através do conceito de herança. 

Em seguida, chamamos o método `acelerar(50)`. No entanto, esse método não está definido na classe `CarroEletrico`, mas sim na classe `Carro`. Portanto, o método `acelerar()` é herdado pela classe `CarroEletrico`. Neste caso, estamos tentando acelerar o carro a uma velocidade de 50 km/h. A saída dessa chamada é a mensagem "Acelerando o carro.".

Após isso, chamamos o método `mostrar_carga_bateria()`, que está definido na classe `CarroEletrico`. Esse método retorna uma string com a carga atual da bateria do carro elétrico, bem como o percentual correspondente. No momento da chamada, a carga da bateria é de 22.5 kWh, o que representa 30.0% da capacidade total da bateria (75 kWh).

Finalmente, realizamos a operação de carregamento, chamando o método `carregar(20)`. Esse método aumenta a carga da bateria em 20 kWh. Após essa operação, chamamos novamente o método `mostrar_carga_bateria()`, e a saída exibe a carga atual da bateria, que agora é de 42.5 kWh, representando 56.7% da capacidade total da bateria.

### Carro a Combustão

```python
class Carro:
    --snip--

class CarroCombustao(Carro):
    def __init__(self, marca, modelo, ano, capacidade_tanque):
        super().__init__(marca, modelo, ano)
        self.capacidade_tanque = capacidade_tanque
        self.volume_combustivel = 1.3 * capacidade_tanque

    def abastecer(self, volume):
        if self.volume_combustivel + volume <= self.volume_tanque:
            self.volume_combustivel += volume
            return "Abastecimento realizado com sucesso."
        else:
            return "Tanque de combustível não comporta esse volume."

    def mostrar_nível_combustivel(self):
        percentual_combustivel = (self.volume_combustivel / self.capacidade_tanque) * 100
        return f"Nível de combustível: {self.volume_combustivel:.1f} litros ({percentual_combustivel:.1f}%)."

# Criando um objeto Carro Combustível
fusion = CarroCombustivel("Ford", "Fusion", 2022, 60)

# Chamando os métodos
print(fusion.ligar())  # Saída: O motor foi ligado.
print(fusion.acelerar(50))  # Saída: Acelerando o carro.
print(fusion.mostrar_nivel_combustivel())  # Saída: Nível de combustível: 20 litros.

# Abastecendo o carro
fusion.abastecer(30)  # Abastecendo com 30 litros de combustível
print(fusion.mostrar_nivel_combustivel())  # Saída: Nível de combustível: 50 litros.
```

Neste exemplo, a classe `CarroCombustao` herda todos os métodos da classe `Carro`, incluindo `ligar()`, `acelerar()` e `descrever()`. Além disso, possui métodos específicos como `abastecer()` para adicionar combustível ao tanque e `mostrar_nivel_combustivel()` para exibir o nível atual de combustível.

Em seguida estamos criando um objeto da classe `CarroCombustivel`, denominado `fusion`. Este carro é um modelo Ford Fusion do ano 2022, com um tanque de capacidade de 60 litros. 

O método `ligar()` é invocado para iniciar o motor do carro. 

Posteriormente, chamamos o método `acelerar(50)`, que acelera o carro em 50 km/h. 

Utilizamos o método `mostrar_nivel_combustivel()` para exibir o nível atual de combustível no tanque do carro. Por exemplo, se o tanque estiver com 20 litros de combustível, a saída será "Nível de combustível: 20 litros."

Em seguida, invocamos o método `abastecer(30)` para adicionar 30 litros de combustível ao tanque do carro. Após o abastecimento, o nível de combustível no tanque será aumentado em 30 litros.

Por fim, utilizamos novamente o método `mostrar_nivel_combustivel()` para exibir o novo nível de combustível no tanque do carro após o abastecimento. Se o tanque estiver com 50 litros de combustível após o abastecimento, a saída será "Nível de combustível: 50 litros."

### Faça agora mesmo !

#### Exercício 8.4:

**Exercício de Herança: Animal e seus Tipos**

Imagine que você está desenvolvendo um sistema para um zoológico, e precisa criar uma hierarquia de classes para representar diferentes tipos de animais. Sua tarefa é criar as classes necessárias utilizando o conceito de herança em Python.

1. Defina uma classe base chamada `Animal`, que possui os seguintes atributos:
   - `nome`: uma string que representa o nome do animal.
   - `idade`: um inteiro que representa a idade do animal em anos.

2. Crie uma classe derivada chamada `Mamifero`, que herda da classe `Animal`. Esta classe deve ter um atributo adicional:
   - `tipo_pelo`: uma string que representa o tipo de pelo do mamífero.

3. Crie outra classe derivada chamada `Ave`, que também herda da classe `Animal`. Esta classe deve ter um atributo adicional:
   - `cor_penas`: uma string que representa a cor das penas da ave.

4. Agora, crie uma classe específica chamada `Cachorro`, que herda da classe `Mamifero`. Esta classe deve ter um método adicional:
   - `latir()`: que retorna uma mensagem indicando que o cachorro está latindo.

5. Por fim, crie uma classe específica chamada `Papagaio`, que herda da classe `Ave`. Esta classe deve ter um método adicional:
   - `falar()`: que retorna uma mensagem indicando que o papagaio está falando.

Você precisa criar as classes conforme explicado, garantindo que a herança seja aplicada corretamente. Certifique-se de definir os atributos e métodos de cada classe conforme as especificações fornecidas. Não se esqueça de criar instâncias das classes e testar os métodos adicionais para garantir que funcionem como esperado.

### Curiosidade: As visões criativas de Nikola Tesla

Nikola Tesla nasceu em Smiljan, uma pequena aldeia na região montanhosa de Lika, que hoje pertence à Croácia, em 10 de julho de 1856. Ele foi um inventor, engenheiro elétrico e físico renomado, cujas contribuições tiveram um impacto significativo na história da eletricidade e da tecnologia moderna.

Uma de suas invenções mais marcantes e influentes foi o sistema de corrente alternada (AC), que revolucionou a distribuição de energia elétrica em larga escala. Ao contrário do sistema de corrente contínua (DC) proposto por Thomas Edison, o AC permitia a transmissão de eletricidade a longas distâncias com eficiência, tornando possível o desenvolvimento de redes elétricas em todo o mundo. A implementação do sistema AC de Tesla foi fundamental para a construção de usinas hidrelétricas e para o fornecimento de eletricidade a cidades inteiras, impulsionando a Revolução Industrial e transformando a vida cotidiana das pessoas.

Tesla também é conhecido por muitas outras invenções e descobertas, incluindo a bobina de Tesla, o motor de indução e contribuições importantes para o desenvolvimento da comunicação sem fio e do rádio. Sua genialidade e visão futurista continuam a inspirar cientistas, engenheiros e inventores até os dias de hoje.

Uma curiosidade fascinante sobre Nikola Tesla, o cientista e inventor, é que ele alegou ter tido visões e ideias que o ajudaram a criar algumas de suas invenções mais revolucionárias. Tesla afirmou que muitas de suas ideias e conceitos surgiram em visões vívidas e intuitivas, às vezes acompanhadas por flashes de luz e imagens em sua mente. Ele descreveu essas visões como uma espécie de insight criativo que o guiou no desenvolvimento de tecnologias como a corrente alternada, a bobina de Tesla e o rádio. Essa narrativa sobre a inspiração de Tesla adiciona uma camada de mistério e maravilha à sua já incrível história como um dos maiores gênios da era moderna.

![A Lenda da Maçã e a Descoberta de Newton](/Images/isaac-newton-apple.png "A Lenda da Maçã e a Descoberta de Newton")

### Exercícios práticos

Agora é hora de praticar o que aprendemos! Aqui estão alguns exercícios para você fazer para testar seus conhecimentos.

#### Exercício 8.5:
Escreva um programa Python que crie uma lista chamada "frutas" contendo os seguintes elementos: "maçã", "banana", "laranja", "uva" e "abacaxi". Em seguida, imprima a lista na tela. 


