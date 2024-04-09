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

Lembre-se de salvar o arquivo com o nome "numeros_pi.txt".

Vamos revisar este código para compreender mais detalhes:

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

### Entendendo Exceções em Python

Sem tratamento de exceções, se mudarmos o nome do arquivo ou se ele não existir, o Python lançará uma exceção e interromperá a execução do programa. Isso resultará em uma mensagem de erro não tratada, o que pode fazer com que o programa pare de funcionar abruptamente e não forneça nenhuma informação útil sobre o problema.

Se, por exemplo, o arquivo "numeros_pi.txt" for renomeado para "numeros_pi2.txt" e tentarmos executar o código original sem tratamento de exceções, receberíamos um erro semelhante ao seguinte:

```
FileNotFoundError: [Errno 2] No such file or directory: 'numeros_pi.txt'
```

Este erro indica que o arquivo especificado não foi encontrado. Sem tratamento de exceções, o programa simplesmente pararia de funcionar e não continuaríamos a obter o número Pi concatenado como esperado.

Em Python, exceções são eventos que ocorrem durante a execução de um programa e interrompem o fluxo normal de operações devido a algum tipo de erro ou condição anormal. Ao lidar com exceções, podemos controlar como nosso programa responde a situações imprevistas.

Considere o seguinte código, onde tentamos ler o conteúdo de um arquivo e concatenar suas linhas em uma única string representando o número Pi. Se o arquivo especificado não existir ou se ocorrer um erro de entrada/saída durante a leitura do arquivo, nosso programa pode falhar.

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

Em Python, um erro de entrada/saída (I/O) ocorre quando há um problema durante a operação de leitura ou escrita de dados em um arquivo ou dispositivo de entrada/saída, como um disco rígido, uma rede ou um dispositivo USB. Esses erros podem surgir de várias maneiras, como arquivos que não podem ser abertos, permissões de arquivo inadequadas, dispositivos que não estão disponíveis ou interrupções na comunicação de rede. No contexto do exemplo dado, um erro de entrada/saída poderia ocorrer, por exemplo, se tentássemos ler um arquivo que está corrompido, se não tivermos permissões suficientes para acessar o arquivo ou se o disco no qual o arquivo está armazenado estiver cheio ou danificado.

Nos blocos `except`, capturamos essas exceções específicas e exibimos mensagens de erro personalizadas. O bloco `else` é opcional e é executado se nenhum erro ocorrer dentro do bloco `try`, onde imprimimos a string `pi_string` que contém o número Pi lido do arquivo.









