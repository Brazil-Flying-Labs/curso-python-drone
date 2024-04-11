## Encontro 8 - Explorando Arquivos e Tratando Exceções

Neste capítulo vamos explorar uma das funcionalidades mais poderosas e empolgantes da linguagem Python: o manuseio de arquivos e o tratamento de exceções. Prepare-se para desvendar os segredos dos arquivos e descobrir como lidar com imprevistos de forma inteligente e eficaz. Ao longo deste capítulo, vamos aprender a ler e escrever em arquivos, mergulhando no mundo de possibilidades que eles nos proporcionam. Além disso, vamos desvendar o conceito de exceções e dominar as técnicas para lidar com elas com maestria. Prontos para essa aventura emocionante? Então, vamos lá!

### O que são Arquivos?

Os arquivos são elementos essenciais no mundo da computação, pois nos permitem armazenar e recuperar informações de forma permanente. Podemos pensar neles como caixas mágicas onde guardamos nossos dados mais preciosos, como textos, imagens, vídeos e muito mais.

Imagine um arquivo como uma gaveta em um armário. Cada gaveta pode conter diferentes tipos de itens, e assim como as gavetas, os arquivos podem armazenar uma variedade de conteúdos, desde simples textos até informações complexas de programas de computador.

Em Python, podemos criar, abrir, ler, escrever e manipular arquivos de diversas maneiras. Essa flexibilidade nos permite criar aplicativos poderosos que lidam com grandes quantidades de dados e realizam tarefas complexas de forma eficiente.

Ao explorar o mundo dos arquivos, vamos descobrir como podemos acessar informações armazenadas em arquivos existentes, criar novos arquivos, escrever dados neles e até mesmo organizar e estruturar nossos dados de forma inteligente.

Entender como trabalhar com arquivos é fundamental para qualquer programador, pois nos permite interagir com o mundo real de maneira digital e criar soluções inteligentes para uma variedade de problemas.

### Lendo de um Arquivo de uma só vez

Para começar, vamos criar manualmente nosso arquivo "numeros_pi.txt" e preenchê-lo com três partes do número Pi. Cada parte será escrita em uma linha separada.

```
3.14
159
265
```

Ao criar o arquivo "numeros_pi.txt", é importante considerar que, ao final de cada linha, deve ser incluída uma quebra de linha, representada como `<enter>`. Lembre-se também de salvar o arquivo com o nome "numeros_pi.txt".

Vamos agora abrir o arquivo, ler o seu conteúdo e exibir na tela:

```python
with open('numeros_pi.txt', 'r') as arquivo:
    conteudo = arquivo.read()
    print(conteudo)
```

Aqui, utilizamos `open()` para acessar o arquivo "numeros_pi.txt" em modo de leitura (`'r'`). Este modo nos permite apenas ler o conteúdo do arquivo, sem modificá-lo. É importante notar que o arquivo "numeros_pi.txt" deve estar localizado no mesmo diretório que nosso script Python, pois não especificamos um caminho absoluto para o arquivo.

Ao utilizar o contexto `with`, garantimos que o arquivo será fechado automaticamente após a conclusão das operações dentro do bloco `with`. Isso é crucial para evitar vazamentos de recursos e problemas de manipulação de arquivo. Quando o código sai da indentação do bloco `with`, o arquivo é automaticamente fechado, mesmo que ocorram erros durante a execução do código.

Dentro do bloco `with`, utilizamos `arquivo.read()` para ler todo o conteúdo do arquivo e armazená-lo na variável `conteudo`. A função `read()` não recebe parâmetros neste exemplo, o que significa que ela lê todo o conteúdo do arquivo de uma vez. No entanto, é importante observar que é possível passar um argumento para `read()` indicando o número máximo de bytes a serem lidos.

Por fim, utilizamos `print(conteudo)` para exibir o conteúdo do arquivo na tela. Esta é uma forma simples de visualizar o que foi lido do arquivo "numeros_pi.txt".

```
3.14
159
265
```

A saída em múltiplas linhas ocorre porque o conteúdo do arquivo "numeros_pi.txt" contém quebras de linha. Quando usamos `arquivo.read()`, todo o conteúdo do arquivo é lido, incluindo essas quebras de linha. Ao imprimir o conteúdo com `print(conteudo)`, o Python reproduz as quebras de linha conforme estão presentes no arquivo, resultando em uma saída em várias linhas.

Os caracteres ocultos que podem estar presentes no arquivo, e que afetam a maneira como as quebras de linha são interpretadas, podem variar entre sistemas operacionais como Windows e Linux.

- No Windows, os caracteres ocultos geralmente são uma combinação de carriage return (`\r`) e new line (`\n`). Isso significa que cada quebra de linha no arquivo pode ser representada por `\r\n`.
- No Linux, as quebras de linha normalmente são representadas apenas por newline (`\n`).

Quando o Python lê o arquivo, ele interpreta esses caracteres ocultos de acordo com o sistema operacional em que está sendo executado. No entanto, ao imprimir o conteúdo, o Python normalmente converte esses caracteres ocultos em quebras de linha visíveis para facilitar a leitura.

Assim, a saída do código pode exibir o conteúdo lido do arquivo em múltiplas linhas, com base na forma como os caracteres ocultos são interpretados pelo Python.

### Lendo de um Arquivo linha a linha

Vamos expandir nosso entendimento com um novo código que lê o arquivo "numeros_pi.txt" linha por linha e remove os caracteres ocultos de quebra:

```python
with open('numeros_pi.txt', 'r') as arquivo:
    for linha in arquivo:
        print(linha.strip(), end=' ')
```

Neste exemplo, estamos abrindo o arquivo "numeros_pi.txt" em modo de leitura (`'r'`) da mesma forma que antes. No entanto, em vez de usar `arquivo.read()` para ler todo o conteúdo do arquivo de uma vez, estamos utilizando um loop `for` para iterar sobre cada linha do arquivo.

O loop `for linha in arquivo:` irá ler o arquivo linha por linha, executando o bloco de código dentro do loop para cada linha encontrada. Esta é uma abordagem mais eficiente em termos de memória, especialmente para arquivos grandes, já que não armazena todo o conteúdo do arquivo na memória de uma vez.

Dentro do loop, estamos usando `print()` para imprimir cada linha do arquivo após remover os caracteres ocultos de quebra. A função `strip()` é utilizada para remover espaços em branco e caracteres de quebra de linha do início e do final de cada linha. O parâmetro `end=' '` em `print()` é utilizado para evitar que `print()` adicione uma quebra de linha adicional após cada linha impressa, substituindo por um espaço em branco, garantindo que a saída permaneça na mesma linha que a saída do `print()` anterior.

Esta é outra forma de visualizar o que foi lido do arquivo "numeros_pi.txt".

```
3.14 159 265
```

Essa abordagem nos permite processar o arquivo linha por linha, o que pode ser útil em situações onde o tamanho do arquivo é muito grande para ser lido de uma vez ou quando queremos processar cada linha individualmente. Além disso, remover os caracteres ocultos de quebra de linha garante que a saída seja exibida em uma única linha, proporcionando uma apresentação mais limpa do conteúdo do arquivo.

Vamos explorar uma variante deste código que gera uma única string contendo todas as linhas do texto lido, concatenadas em um único número:

```python
pi_string = ''  # Inicializamos uma string vazia para armazenar as linhas concatenadas

with open('numeros_pi.txt', 'r') as arquivo:
    for linha in arquivo:
        pi_string += linha.strip()  # Concatenamos cada linha, removendo caracteres de quebra

print(pi_string)  # Imprimimos a string resultante contendo o número de Pi
```

Neste exemplo, inicializamos a variável `pi_string` como uma string vazia. Dentro do bloco `with`, percorremos cada linha do arquivo "numeros_pi.txt" usando um loop `for`. Para cada linha, removemos os caracteres de quebra utilizando `strip()` e então concatenamos a linha à variável `pi_string` utilizando o operador de concatenação `+=`.

Dessa forma, ao final do loop, `pi_string` conterá todas as linhas do arquivo concatenadas em um único número. Finalmente, imprimimos essa string resultante que representa o número Pi. Esta abordagem é útil quando queremos processar o conteúdo do arquivo de uma maneira diferente, como, por exemplo, para realizar cálculos ou para gerar um número único para Pi como fizemos aqui.

### Faça agora mesmo !

#### Exercício 8.1: 

Crie um arquivo de texto chamado "introducao.txt" e escreva algumas frases interessantes sobre um tema que você goste. Em seguida, escreva um programa Python que abra o arquivo "introducao.txt", leia seu conteúdo e o exiba na tela. Faça uma pequena alteração no arquivo "introducao.txt" e observe como a mudança afeta a saída do programa.

#### Exercício 8.2: 

Busque um texto interessante na internet, copie e cole esse texto no arquivo "texto.txt". Em seguida, escreva um programa Python que abra o arquivo "texto.txt", leia seu conteúdo e conte o número total de palavras no texto. VOcê pode utilizar a função `open()` para abrir o arquivo, `read()` para ler seu conteúdo e `split()` para dividir o texto em palavras. Depois, basta utilizar a função `len()` para contar o número de palavras resultantes da divisão.

### Entendendo Exceções em Python

Sem tratamento de exceções, se mudarmos o nome do arquivo sendo lido nos exemplos anteriores, ou se eles não existirem, o Python lançará uma exceção e interromperá a execução do programa. Isso resultará em uma mensagem de erro não tratada, o que pode fazer com que o programa pare de funcionar abruptamente e não forneça nenhuma informação útil sobre o problema.

Se, por exemplo, o arquivo "numeros_pi.txt" for renomeado para "numeros_pi2.txt" e tentarmos executar o código original sem tratamento de exceções, receberíamos um erro semelhante ao seguinte:

```
FileNotFoundError: [Errno 2] No such file or directory: 'numeros_pi.txt'
```

Este erro indica que o arquivo especificado não foi encontrado. Sem tratamento de exceções, o programa simplesmente pararia de funcionar e não continuaríamos a obter o número Pi concatenado como esperado.

Em Python, exceções são eventos que ocorrem durante a execução de um programa e interrompem o fluxo normal de operações devido a algum tipo de erro ou condição anormal. Ao lidar com exceções, podemos controlar como nosso programa responde a situações imprevistas.

Para lidar com essas situações, podemos utilizar blocos `try`, `except` e `else`. No bloco `try`, colocamos o código que queremos executar, enquanto nos blocos `except`, capturamos e tratamos exceções específicas que podem ocorrer durante a execução do código dentro do bloco `try`.

No exemplo abaixo, utilizamos tratamento de exceções para lidar com possíveis erros ao abrir ou ler o arquivo:

```python
pi_string = ''

try:
    with open('numeros_pi.txt', 'r') as arquivo:
        for linha in arquivo:
            pi_string += linha.strip()  
except FileNotFoundError as e:
    print(f"O arquivo 'numeros_pi.txt' não foi encontrado. Erro: {e}")
except IOError as e:
    print(f"Erro ao ler o arquivo 'numeros_pi.txt'. Erro: {e}")
else:
    print(pi_string) 
```

Dentro do bloco `try`, tentamos abrir e ler o arquivo "numeros_pi.txt". Se o arquivo não for encontrado, uma exceção `FileNotFoundError` será levantada. Se ocorrer um erro de entrada/saída durante a leitura do arquivo, uma exceção `IOError` será levantada. 

Em Python, um erro de entrada/saída `IOError` ocorre quando há um problema durante a operação de leitura ou escrita de dados em um arquivo ou dispositivo de entrada/saída, como um disco rígido, uma rede ou um dispositivo USB. Esses erros podem surgir de várias maneiras, como arquivos que não podem ser abertos, permissões de arquivo inadequadas, dispositivos que não estão disponíveis ou interrupções na comunicação de rede. No contexto do exemplo dado, um erro de entrada/saída poderia ocorrer, por exemplo, se tentássemos ler um arquivo que está corrompido, se não tivermos permissões suficientes para acessar o arquivo ou se o disco no qual o arquivo está armazenado estiver cheio ou danificado.

Nos blocos `except`, capturamos essas exceções específicas e exibimos mensagens de erro personalizadas. O bloco `else` é opcional e é executado se nenhum erro ocorrer dentro do bloco `try`, onde imprimimos a string `pi_string` que contém o número Pi lido do arquivo.

A beleza deste programa vai além da simples exibição do número Pi. Ele é um exemplo vivo do poder do tratamento de exceções em Python. Ao envolver nosso código em um escudo protetor de tratamento de exceções, garantimos que mesmo nos momentos mais turbulentos, como quando o arquivo "numeros_pi.txt" não é encontrado ou ocorrem erros de leitura, nosso programa não apenas sobrevive, mas também nos dá a chance de lidar com esses problemas com elegância.

### Faça agora mesmo !

#### Exercício 8.3: 

Agora que você aprendeu sobre abertura de arquivos e leitura de conteúdo em Python, é hora de tornar seus programas mais robustos adicionando tratamento de exceções! Reescreva os exercícios 8.1 e 8.2 anteriores, mas desta vez adicione blocos de tratamento de exceções para lidar com possíveis erros que possam ocorrer durante a execução do programa.

### Escrevendo em um novo arquivo

Nesta etapa, vamos avançar em nossa jornada de aprendizado e explorar como podemos armazenar informações importantes em arquivos usando Python. Imagine que possuímos o número Pi concatenado, um conjunto valioso de dados que desejamos preservar para uso futuro. Ao invés de apenas exibirmos esse valor na tela, aprenderemos a gravá-lo em um arquivo denominado "pi_concatenado.txt".

Ao trabalharmos com a escrita em arquivos, devemos entender alguns conceitos fundamentais. Utilizaremos a função `open()` para abrir um arquivo no modo de escrita, indicando isso por meio do parâmetro `'w'`. Se o arquivo especificado não existir, o Python irá criá-lo automaticamente. A função `write()` será nossa aliada para inserir conteúdo no arquivo aberto para escrita. Neste caso, utilizaremos essa função para gravar o número Pi concatenado no arquivo "pi_concatenado.txt". 

Vamos aplicar esses conceitos em nosso exemplo prático:

```python
pi_string = ''

try:
    with open('numeros_pi.txt', 'r') as arquivo:
        for linha in arquivo:
            pi_string += linha.strip()  
except FileNotFoundError as e:
    print(f"O arquivo 'numeros_pi.txt' não foi encontrado. Erro: {e}")
except IOError as e:
    print(f"Erro ao ler o arquivo 'numeros_pi.txt'. Erro: {e}")
else:
    with open('pi_concatenado.txt', 'w') as arquivo_saida:
        arquivo_saida.write(pi_string)
        print("Número Pi concatenado foi gravado com sucesso em 'pi_concatenado.txt'!")
``` 

Este código em Python representa um processo essencial na manipulação de arquivos: a leitura de um arquivo existente, o processamento de seu conteúdo e a escrita desse conteúdo em um novo arquivo. No contexto específico deste exemplo, o programa lida com o número Pi, que é lido a partir de um arquivo denominado "numeros_pi.txt".

Ao iniciar a execução, o programa tenta abrir o arquivo "numeros_pi.txt" para leitura. Utiliza-se um bloco `try-except` para lidar com possíveis erros durante esse processo, tais como o arquivo não ser encontrado ou ocorrer um erro de leitura. Se o arquivo for aberto com sucesso, o programa itera sobre cada linha do arquivo, removendo espaços em branco e caracteres de nova linha, e concatena essas linhas em uma única string chamada `pi_string`.

A etapa seguinte envolve a escrita dessa string no arquivo "pi_concatenado.txt". Para isso, o programa abre o arquivo em modo de escrita ('w'). Se o arquivo já existir, seu conteúdo anterior será substituído pelo novo conteúdo; caso contrário, um novo arquivo será criado. Em seguida, utiliza-se o método `write()` para gravar o conteúdo da variável `pi_string` no arquivo.

Após a operação de escrita ser concluída com sucesso, uma mensagem é exibida na tela, informando que o número Pi concatenado foi gravado com sucesso no arquivo "pi_concatenado.txt".

Agora vamos criar um outro exemplo onde armazenamos informações em múltiplas linhas em um arquivo. Suponha que queremos armazenar informações sobre pessoas em um arquivo de texto, onde cada linha representa uma pessoa e contém seu nome, idade e cidade.

```python
# Dados das pessoas
pessoas = [
    ["João", 30, "São Paulo"],
    ["Maria", 25, "Rio de Janeiro"],
    ["Pedro", 35, "Belo Horizonte"]
]

# Abre o arquivo para escrita
with open('pessoas.txt', 'w') as arquivo_saida:
    # Escreve os dados de cada pessoa no arquivo
    for pessoa in pessoas:
        arquivo_saida.write(f"Nome: {pessoa[0]}\n")
        arquivo_saida.write(f"Idade: {pessoa[1]}\n")
        arquivo_saida.write(f"Cidade: {pessoa[2]}\n")  
        arquivo_saida.write("\n")  # Quebra de linha entre as pessoas

print("Dados das pessoas foram gravados com sucesso em 'pessoas.txt'!")
```

Após escrever os dados de cada pessoa no arquivo, adicionamos uma quebra de linha `\n`. Além disso, uma outra quebra de linha `arquivo_saida.write("\n")` cria uma separação entre as informações de cada pessoa. Isso é feito para tornar o arquivo mais legível, facilitando a identificação de onde uma pessoa termina e a próxima começa.

A quebra de linha é representada pelo caractere `\n`, que é um caractere especial que indica uma nova linha no texto. Quando esse caractere é escrito no arquivo, ele faz com que o cursor de escrita avance para a próxima linha, garantindo que a próxima pessoa seja escrita em uma nova linha no arquivo. Isso cria uma separação visual entre as informações de cada pessoa, facilitando a leitura e a compreensão do arquivo.

### Adicionando dados em um arquivo existente

Em Python, para adicionar conteúdo a um arquivo existente sem sobrescrevê-lo, você pode abrir o arquivo no modo de escrita com o parâmetro `'a'` (append). Aqui está como usar a função `open()` com o parâmetro `'a'`:

```python
with open('arquivo.txt', 'a') as arquivo:
    arquivo.write("Nova linha a ser adicionada.\n")
```

Neste exemplo, a função `open()` é utilizada para abrir o arquivo "arquivo.txt" no modo de escrita, mas com o parâmetro `'a'` (append). Isso significa que o Python irá abrir o arquivo para escrita, mas adicionará novos conteúdos ao final do arquivo existente, em vez de sobrescrevê-lo.

Em seguida, a função `write()` é usada para adicionar uma nova linha de texto ao arquivo. É importante incluir o caractere de nova linha ('\n') no final do texto adicionado para garantir que cada adição seja colocada em uma nova linha no arquivo. Isso evita que os novos conteúdos sejam concatenados à última linha existente no arquivo.

### Curiosidade: O Fascinante Papiro de Rhind e o Enigma do Número Pi

O Papiro de Rhind, uma das mais preciosas relíquias do Egito Antigo, é um rolo de papiro datado de aproximadamente 1650 a.C. Esse papiro, também conhecido como Papiro de Ahmes em homenagem ao seu suposto autor, o escriba Ahmes, revela um tesouro de conhecimentos matemáticos e problemas que intrigaram gerações ao longo dos séculos.

Uma das descobertas mais fascinantes contidas neste antigo manuscrito é a referência ao número Pi, uma constante matemática que representa a relação entre a circunferência de um círculo e seu diâmetro. Através de uma fórmula antiga, o Papiro de Rhind fornece uma aproximação surpreendentemente precisa do valor de Pi, embora expresso de forma diferente da que estamos acostumados hoje.

O Papiro de Rhind não é apenas um registro de cálculos matemáticos; é um testemunho da engenhosidade e da busca do conhecimento que impulsionaram as civilizações antigas. No entanto, o mais fascinante é que, apesar de ter sido escrito há milhares de anos, suas lições e desafios matemáticos ainda ecoam nos corredores da educação moderna, inspirando alunos e acadêmicos a explorar os mistérios da matemática.

Uma das curiosidades intrigantes sobre o Papiro de Rhind é a sua origem incerta e a jornada que fez ao longo dos séculos até chegar aos olhos dos estudiosos modernos. Apesar de ser nomeado em homenagem a um escriba chamado Ahmes, sua autoria exata e o contexto de sua criação permanecem envoltos em mistério. Este antigo manuscrito foi adquirido pelo matemático escocês Alexander Henry Rhind em meados do século XIX, durante suas viagens ao Egito. Rhind adquiriu o papiro de um vendedor de antiguidades no Cairo, juntamente com outros artefatos egípcios. Desde então, o Papiro de Rhind foi preservado em várias coleções, incluindo a Biblioteca Britânica em Londres, onde permanece como um tesouro valioso para estudiosos e entusiastas da matemática e da história antiga.

Essa curiosidade sobre a jornada do Papiro de Rhind através do tempo e das mãos de diferentes colecionadores e estudiosos adiciona uma camada fascinante à sua história. É um lembrete do valor dos registros históricos e da importância de preservar e estudar o passado para compreender melhor o presente e o futuro.

![O Fascinante Papiro de Rhind e o Enigma do Número Pi](/Images/papiro-rhind-pi.jpg "O Fascinante Papiro de Rhind e o Enigma do Número Pi")

### Exercícios práticos

Agora é hora de praticar o que aprendemos! Aqui estão alguns exercícios para você fazer para testar seus conhecimentos.

#### Exercício 8.5:

Escreva um programa Python que solicite ao usuário que insira uma lista de números inteiros separados por vírgula. Em seguida, armazene esses números em um arquivo de texto chamado "numeros.txt", um por linha. Certifique-se de lidar com possíveis erros de entrada do usuário.

Neste exemplo, a `função split(',')` pode ser utilizada para dividir a entrada do usuário em uma lista de strings, utilizando a vírgula como delimitador, criando assim a lista numeros com os números lidos. VOcê pode usar essa lista para escrever os números no arquivo "numeros.txt".

#### Exercício 8.6:

Desenvolva um programa que leia o conteúdo do arquivo "numeros.txt" criado no exercício anterior e exiba a soma de todos os números presentes no arquivo. Caso o arquivo não exista ou ocorra algum problema durante a leitura, exiba uma mensagem amigável ao usuário.

Uma dica útil para você resolver esse problema é utilizar a função int() para converter as strings lidas do arquivo em números inteiros, e depois realizar a soma dos números.

#### Exercício 8.7:

Escreva um programa Python que tente abrir um arquivo chamado "dados.txt" para escrita. Em seguida, continue o programa solicitando ao usuário que insira novos dados e escreva esses dados no arquivo. 

#### Exercício 8.8:

Crie um programa que leia um arquivo de texto chamado "texto.txt" e conte o número de palavras presentes no arquivo. Em seguida, exiba esse número para o usuário. Certifique-se de lidar adequadamente com a abertura do arquivo e possíveis erros de leitura.

#### Exercício 8.9:

Desenvolva um programa que permita ao usuário buscar por uma palavra-chave em um arquivo de texto. O programa deve solicitar ao usuário que insira a palavra-chave e, em seguida, verificar se ela está presente no arquivo "texto.txt". Se a palavra-chave for encontrada, o programa deve exibir a linha em que ela está presente. Caso contrário, deve informar que a palavra não foi encontrada.

Um desafio comum ao lidar com arquivos de texto em Python é buscar por uma palavra-chave dentro de um arquivo e exibir a linha em que ela está presente. Para resolver este problema, você pode seguir os seguintes passos:

1. Abertura do Arquivo: Utilize a função `open()` para abrir o arquivo de texto em modo de leitura ('r'). Isso permite que o programa acesse o conteúdo do arquivo.

2. Entrada da Palavra-Chave: Solicite ao usuário que insira a palavra-chave que deseja buscar. Isso pode ser feito utilizando a função `input()`.

3. Busca por Palavra-Chave: Utilize um loop para percorrer cada linha do arquivo de texto. Para cada linha, verifique se a palavra-chave está presente utilizando o método `in` ou o método `find()`.

4. Exibição da Linha: Se a palavra-chave for encontrada em uma linha, exiba essa linha para o usuário. Caso contrário, informe que a palavra não foi encontrada.

