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

Agora que nosso arquivo "numeros_pi.txt" está pronto, vamos utilizar Python para abrir e ler o seu conteúdo. O código abaixo mostra como podemos fazer isso:

```python
try:
    with open('numeros_pi.txt', 'r') as arquivo:
        conteudo = arquivo.read()
        print(conteudo)
except FileNotFoundError:
    print("O arquivo não pôde ser encontrado. Verifique se o nome do arquivo está correto.")
except IOError:
    print("Ocorreu um erro ao tentar ler o arquivo. Verifique se você tem permissão para acessá-lo.")
```

Neste código, estamos utilizando um bloco `try-except` para lidar com possíveis erros que podem ocorrer durante a leitura do arquivo. 

Dentro do bloco `try`, utilizamos a função `open()` para abrir o arquivo "numeros_pi.txt" em modo de leitura (`'r'`). Em seguida, utilizamos o método `read()` para ler todo o conteúdo do arquivo e armazená-lo na variável `conteudo`. Por fim, imprimimos o conteúdo na tela utilizando a função `print()`.

Caso o arquivo não seja encontrado, o Python irá levantar uma exceção do tipo `FileNotFoundError`, e uma mensagem de erro será exibida informando que o arquivo não pôde ser encontrado. Se ocorrer um erro de leitura durante o processo, uma exceção do tipo `IOError` será levantada, indicando que houve um problema ao tentar ler o arquivo.

Em termos simples, podemos pensar em exceções como erros inesperados que ocorrem durante a execução do programa. Esses erros podem ser causados por várias razões, como tentar acessar um arquivo que não existe, fazer uma divisão por zero, ou tentar acessar um índice inválido em uma lista, entre outros.

As exceções são importantes porque permitem que os programas lidem com erros de maneira mais elegante, evitando que eles interrompam abruptamente a execução do programa. Em vez disso, o programa pode capturar e tratar a exceção, fornecendo uma mensagem de erro útil para o usuário ou tomando medidas alternativas para lidar com a situação problemática.

Por exemplo, se um programa estiver tentando abrir um arquivo que não existe, uma exceção do tipo FileNotFoundError será levantada. O programa pode capturar essa exceção e exibir uma mensagem amigável para o usuário, informando que o arquivo não pôde ser encontrado e fornecendo instruções sobre o que fazer em seguida.

### Lendo de um Arquivo linha a linha

No exemplo anterior, usamos o método read() para ler todo o conteúdo do arquivo de uma só vez e armazená-lo em uma variável. Isso significa que o conteúdo inteiro do arquivo é carregado na memória de uma vez só. Isso pode ser eficiente para arquivos pequenos, mas pode ser problemático para arquivos grandes, pois consome muita memória.

Vamos criar um exemplo em Python para ler o arquivo "numeros_pi.txt" linha por linha e, em seguida, explicar como isso difere da leitura do arquivo inteiro de uma só vez.

```python
try:
    with open('numeros_pi.txt', 'r') as arquivo:
        for linha in arquivo:
            print(linha.strip(), end=' ')
except FileNotFoundError:
    print("O arquivo não pôde ser encontrado. Verifique se o nome do arquivo está correto.")
except IOError:
    print("Ocorreu um erro ao tentar ler o arquivo. Verifique se você tem permissão para acessá-lo.")
```

Este código também utiliza a estrutura `try-except` para lidar com exceções. O bloco `try` é responsável por tentar executar o código dentro dele, enquanto os blocos `except` são usados para lidar com exceções que podem ocorrer durante a execução do código.

Dentro do bloco `try`, abrimos o arquivo "numeros_pi.txt" em modo de leitura (`'r'`) usando a declaração `with open('numeros_pi.txt', 'r') as arquivo:`. Assim como no exemplo anterior, isso garante que o arquivo seja fechado corretamente após a conclusão do bloco `with`.

Dentro do bloco `with`, utilizamos um loop `for` para iterar sobre cada linha do arquivo. Para cada linha, removemos os espaços em branco e quebras de linha usando o método `strip()`. Em seguida, imprimimos a linha na tela usando `print(linha.strip(), end=' ')`, onde `end=' '` é usado para evitar que o `print()` adicione uma nova linha após cada impressão.

A diferença principal entre este exemplo e o exemplo anterior está na maneira como o conteúdo do arquivo é tratado. No exemplo anterior, lemos e concatenamos todas as linhas do arquivo em uma única string antes de imprimi-la na tela. Neste exemplo, no entanto, imprimimos cada linha do arquivo diretamente na tela à medida que as lemos. Isso significa que não estamos armazenando todo o conteúdo do arquivo na memória de uma vez, o que pode ser mais eficiente em termos de uso de memória, especialmente para arquivos grandes.

Se ocorrer um `FileNotFoundError`, o bloco `except FileNotFoundError` será executado, exibindo uma mensagem indicando que o arquivo não pôde ser encontrado. Se ocorrer um `IOError`, o bloco `except IOError` será executado, indicando que ocorreu um erro ao tentar ler o arquivo.

Agora vamos criar um exemplo em Python para ler o arquivo "numeros_pi.txt" linha por linha e, em seguida, concatenar as linha para gerar um número PI único.

```python
try:
    with open('numeros_pi.txt', 'r') as arquivo:
        numero_pi = ''
        for linha in arquivo:
            numero_pi += linha.strip()
        print(numero_pi)
except FileNotFoundError:
    print("O arquivo não pôde ser encontrado. Verifique se o nome do arquivo está correto.")
except IOError:
    print("Ocorreu um erro ao tentar ler o arquivo. Verifique se você tem permissão para acessá-lo.")
```

Começamos com a estrutura `try-except`, que é usada para lidar com exceções. O código dentro do bloco `try` é executado, e se ocorrer algum erro, o Python procurará por um bloco `except` correspondente para lidar com a exceção.

Dentro do bloco `try`, abrimos o arquivo "numeros_pi.txt" em modo de leitura (`'r'`) usando a declaração `with open('numeros_pi.txt', 'r') as arquivo:`. Isso garante que o arquivo seja fechado corretamente após a conclusão do bloco `with`, mesmo se ocorrerem erros durante a execução.

Dentro do bloco `with`, inicializamos uma variável chamada `numero_pi` como uma string vazia. Em seguida, usamos um loop `for` para iterar sobre cada linha do arquivo. Para cada linha, removemos os espaços em branco e quebras de linha usando o método `strip()`, e concatenamos a linha atual à variável `numero_pi` usando o operador `+=`.

Após o loop, toda a concatenação é impressa na tela usando `print(numero_pi)`.

Se ocorrer um `FileNotFoundError`, o bloco `except FileNotFoundError` será executado, exibindo uma mensagem indicando que o arquivo não pôde ser encontrado. Se ocorrer um `IOError`, o bloco `except IOError` será executado, indicando que ocorreu um erro ao tentar ler o arquivo.






