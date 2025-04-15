# Capítulo 2: Fundamentos Essenciais: Variáveis, Dados e Operadores

No Capítulo 1, você deu os primeiros passos: entendeu o que é programação, instalou Python e executou seu primeiro script. Agora, vamos começar a trabalhar com o coração de qualquer programa: os **dados**.

Neste capítulo, você aprenderá como armazenar informações usando **variáveis**, conhecerá os **tipos de dados** básicos que Python oferece (números, texto, valores verdadeiro/falso), e como realizar operações com esses dados usando **operadores**. Vamos construir a base para criar programas mais interessantes!

## Deixando Pistas: Comentários no Código

Antes de mergulharmos nas variáveis, vamos falar sobre algo útil: **comentários**. Comentários são trechos de texto no seu código que o interpretador Python ignora completamente. Eles servem para nós, humanos, entendermos melhor o que o código está fazendo.

Em Python, qualquer texto que aparece após o símbolo `#` (cerquilha ou "hashtag") em uma linha é considerado um comentário:

 ```python
# Isto é um comentário. Python vai ignorar esta linha.

print("Isso será executado.") # Isso também é um comentário, após o código.

# Use comentários para:
# 1. Explicar partes complexas do seu código.
# 2. Deixar lembretes para você mesmo ou outros desenvolvedores.
# 3. Desabilitar temporariamente uma linha de código sem apagá-la:
# print("Linha temporariamente desabilitada")
 ```

Bons comentários explicam o *porquê* de algo estar sendo feito, não apenas *o quê* (que o próprio código já deve deixar claro). Use-os com moderação, mas use-os!

* (Nota: Você também pode ver blocos de texto entre aspas triplas `""" ... """` ou `''' ... '''` usados como comentários de múltiplas linhas. Embora o Python os ignore se não estiverem em um local específico, seu uso principal é para algo chamado "docstrings", que servem para documentar funções e módulos, algo que veremos mais adiante.)*

## Guardando Informações: Variáveis

Imagine que você tem caixas de armazenamento e quer guardar coisas nelas. Para saber o que tem em cada caixa, você coloca uma etiqueta. Em programação, uma **variável** é como uma dessas caixas etiquetadas: é um nome que damos a um espaço na memória do computador onde podemos guardar um valor (um dado).

Para criar uma variável em Python e guardar um valor nela, usamos o operador de **atribuição**, que é o sinal de igual `=`.

 ```python
# Criando variáveis e atribuindo valores
nome_do_livro = "Introdução à Programação com Python" # Guarda um texto
ano_publicacao = 2025                             # Guarda um número inteiro
preco = 49.90                                     # Guarda um número decimal
foi_publicado = True                              # Guarda um valor verdadeiro/falso
 ```

**Como funciona:**
* À esquerda do `=`, temos o **nome da variável**.
* À direita do `=`, temos o **valor** que queremos guardar.

Agora, podemos usar o nome da variável para acessar o valor guardado:

 ```python
print(nome_do_livro)
print(ano_publicacao)
 ```

**Nomeando Variáveis:**
Existem regras e convenções para dar nomes às variáveis em Python:
* **Regras (Obrigatórias):**
    * Nomes só podem conter letras (a-z, A-Z), números (0-9) e o caractere underscore (`_`).
    * Nomes **não** podem começar com um número.
    * Nomes são **case-sensitive** (diferenciam maiúsculas de minúsculas): `idade` é diferente de `Idade`.
    * Não podem ser iguais a **palavras-chave reservadas** do Python (como `if`, `else`, `while`, `for`, `def`, `class`, `True`, `False`, `None`, etc.).
* **Convenções (Boas Práticas):**
    * Use nomes **descritivos** que indiquem o propósito da variável (e.g., `nome_completo` em vez de `nc`).
    * Use o estilo **snake_case**: palavras minúsculas separadas por underscore (`_`). Ex: `taxa_juros`, `nome_do_usuario`.
    * Evite usar nomes de funções já existentes (como `print`, `input`, `list`, `str`).

**Reatribuição:** Você pode mudar o valor guardado em uma variável simplesmente atribuindo um novo valor a ela:

 ```python
saldo_conta = 100.0
print(saldo_conta)  # Saída: 100.0

saldo_conta = saldo_conta + 50.0 # Calcula novo saldo
print(saldo_conta)  # Saída: 150.0

saldo_conta = 0.0   # Atribui um valor completamente novo
print(saldo_conta)  # Saída: 0.0
 ```

## Tipos de Dados Primitivos

Os valores que guardamos nas variáveis podem ser de diferentes tipos. Python tem vários tipos de dados embutidos, mas vamos focar nos mais fundamentais, chamados de tipos primitivos:

* Números Inteiros (`int`)
* Números de Ponto Flutuante (`float`)
* Texto (`str` - string)
* Booleanos (`bool`)

Podemos descobrir o tipo de um valor ou variável usando a função `type()`:

 ```python
numero = 10
texto = "Olá"
preco = 9.99
ativo = False

print(type(numero))  # Saída: <class 'int'>
print(type(texto))   # Saída: <class 'str'>
print(type(preco))   # Saída: <class 'float'>
print(type(ativo))   # Saída: <class 'bool'>
 ```

Vamos ver cada um em detalhe:

### Inteiros (`int`)

Representam números inteiros, positivos ou negativos, sem parte decimal.

 ```python
idade = 30
ano = -2024
quantidade_itens = 0
populacao_mundial = 8000000000 # Inteiros podem ser bem grandes

print(type(idade)) # <class 'int'>
 ```

### Ponto Flutuante (`float`)

Representam números que possuem uma parte decimal. O separador decimal em Python (e na maioria das linguagens de programação) é o **ponto** (`.`), não a vírgula.

 ```python
altura = 1.75
preco_produto = 19.99
pi = 3.14159
saldo_negativo = -10.50

print(type(altura)) # <class 'float'>

# Mesmo que a parte decimal seja zero, se houver um ponto, é float:
versao = 1.0
print(type(versao)) # <class 'float'>
 ```

* (Nota: Computadores têm uma forma específica de representar floats internamente, o que às vezes pode levar a pequenas imprecisões em cálculos muito complexos. Para a maioria das aplicações do dia a dia, isso não é um problema, mas é bom saber que existe.)*

### Texto (String - `str`)

Representa sequências de caracteres (letras, números, símbolos, espaços). Em Python, strings são definidas colocando o texto entre aspas simples (`'`) ou aspas duplas (`"`).

 ```python
nome = "Alice"
mensagem = 'Python é divertido!'
codigo_produto = "COD-1234-XPTO"
frase_vazia = ""

print(type(nome)) # <class 'str'>
 ```

**Aspas Simples ou Duplas?** Tanto faz, mas seja consistente dentro do seu projeto. Use aspas duplas se sua string contém aspas simples, e vice-versa:

 ```python
citacao1 = 'Ela disse: "Olá!"'
citacao2 = "O'Malley's Pub"
 ```

Se precisar usar o mesmo tipo de aspas dentro da string, você pode "escapar" a aspa interna com uma barra invertida (`\`):

 ```python
mesmo_tipo = "Ele disse: \"Sim!\""
print(mesmo_tipo) # Saída: Ele disse: "Sim!"
 ```

**Strings de Múltiplas Linhas:** Para textos que ocupam várias linhas, use aspas triplas (simples ou duplas):

 ```python
poema = """
Batatinha quando nasce,
espalha a rama pelo chão.
Menininha quando dorme,
põe a mão no coração.
"""

print(poema)
 ```

### Operações com Strings

Strings são muito usadas, e Python oferece várias operações úteis para elas:

* **Concatenação (+):** Juntar duas ou mais strings.
   ```python
  saudacao = "Olá"
  nome = "Mundo"
  mensagem_completa = saudacao + " " + nome + "!" # Adiciona um espaço entre elas
  print(mensagem_completa) # Saída: Olá Mundo!
   ```

* **Repetição (*):** Repetir uma string um número de vezes.
   ```python
  eco = "Eco! "
  print(eco * 3) # Saída: Eco! Eco! Eco!
   ```

* **Tamanho (`len()`):** Obter o número de caracteres em uma string (incluindo espaços).
   ```python
  frase = "Python rocks"
  tamanho = len(frase)
  print(tamanho) # Saída: 12
   ```

* **Formatação (f-strings):** A forma moderna e recomendada de incluir valores de variáveis dentro de strings. Coloque um `f` antes da aspa inicial da string e, dentro dela, coloque os nomes das variáveis entre chaves `{ }`.
   ```python
  nome = "Carlos"
  idade = 42
  altura = 1.80

  # Forma antiga (concatenação manual, pode ficar confuso)
  # print("Nome: " + nome + ", Idade: " + str(idade)) # Precisa converter idade para str

  # Forma moderna (f-string - mais limpa e eficiente)
  mensagem_formatada = f"Nome: {nome}, Idade: {idade}, Altura: {altura}m"
  print(mensagem_formatada) # Saída: Nome: Carlos, Idade: 42, Altura: 1.8m

  # Você pode até colocar expressões dentro das chaves!
  print(f"Daqui a 5 anos, {nome} terá {idade + 5} anos.")
   ```
  *Nota:* Existem outras formas de formatação de strings em Python (como o método `.format()` ou o operador `%`), mas as f-strings são geralmente preferidas em código moderno (Python 3.6+).

### Booleanos (`bool`)

Representam valores lógicos: verdadeiro ou falso. Só existem dois valores booleanos em Python: `True` e `False` (note as iniciais maiúsculas).

 ```python
usuario_logado = True
email_valido = False
tem_saldo = True

print(type(usuario_logado)) # <class 'bool'>
 ```

Booleanos são fundamentais para controlar o fluxo de um programa usando estruturas condicionais (como `if`), que veremos no próximo capítulo.

**Conversão para Booleano:** Você pode converter outros tipos para booleano usando `bool()`. É útil saber quais valores são considerados "falsos" (`False`) em Python:
* O número zero (`0`, `0.0`)
* Strings vazias (`""`, `''`)
* O valor especial `None` (que representa a ausência de valor)
* Coleções vazias (como listas, tuplas, dicionários vazios - veremos depois)

Qualquer outro valor geralmente é considerado `True`.

 ```python
print(bool(0))      # Saída: False
print(bool(""))      # Saída: False
print(bool(None))   # Saída: False
print(bool(10))     # Saída: True
print(bool(-1.5))   # Saída: True
print(bool("Olá"))  # Saída: True
 ```

## Operadores Aritméticos

Permitem realizar operações matemáticas com números (`int` e `float`).

* **Adição (+):** `a + b`
* **Subtração (-):** `a - b`
* **Multiplicação (*):** `a * b`
* **Divisão (/):** `a / b` -> Sempre resulta em um `float`.
* **Divisão Inteira (//):** `a // b` -> Divide e arredonda o resultado para baixo (para o inteiro mais próximo ou igual). O tipo do resultado depende dos operandos (int//int -> int, float//float -> float).
* **Módulo ou Resto (%):** `a % b` -> Retorna o resto da divisão inteira de `a` por `b`. Útil para verificar se um número é par (`numero % 2 == 0`), entre outras coisas.
* **Exponenciação (`**`):** `a ** b` -> Calcula `a` elevado à potência `b`.

 ```python
a = 10
b = 3

soma = a + b          # 13
diferenca = a - b     # 7
produto = a * b       # 30
divisao_float = a / b # 3.333... (float)
divisao_inteira = a // b # 3 (int)
resto = a % b         # 1 (o resto de 10 dividido por 3 é 1)
potencia = a ** b     # 1000 (10 elevado a 3)

print(f"Soma: {soma}")
print(f"Diferença: {diferenca}")
print(f"Produto: {produto}")
print(f"Divisão Float: {divisao_float}")
print(f"Divisão Inteira: {divisao_inteira}")
print(f"Resto (Módulo): {resto}")
print(f"Potência: {potencia}")

# Cuidado com divisão por zero! Isso causa um erro (ZeroDivisionError)
# print(10 / 0)
 ```

**Ordem de Precedência:** Python segue a ordem matemática padrão das operações (PEMDAS/BODMAS: Parênteses, Exponenciação, Multiplicação/Divisão, Adição/Subtração). Multiplicação/Divisão têm a mesma precedência e são avaliadas da esquerda para a direita. O mesmo vale para Adição/Subtração.

 ```python
resultado1 = 10 + 2 * 3  # Multiplicação primeiro: 10 + 6 = 16
resultado2 = (10 + 2) * 3 # Parênteses primeiro: 12 * 3 = 36

print(resultado1)
print(resultado2)
 ```
Use parênteses `( )` sempre que quiser garantir ou clarear a ordem das operações.

## Coletando Dados do Usuário: `input()`

Muitas vezes, queremos que nossos programas interajam com o usuário, pedindo informações. Para isso, usamos a função `input()`. Ela exibe uma mensagem para o usuário (opcional), espera que ele digite algo e pressione Enter, e então retorna o que foi digitado.

**Importante:** A função `input()` **sempre** retorna o valor digitado pelo usuário como uma **string (`str`)**, mesmo que ele digite números.

 ```python
nome = input("Digite seu nome: ")
cidade = input("Em qual cidade você mora? ")

print(f"Olá, {nome} de {cidade}!")

# Pedindo um número (mas lembre-se, virá como string!)
idade_texto = input("Qual sua idade? ")
print(f"Você digitou a idade: {idade_texto}")
print(f"O tipo da variável 'idade_texto' é: {type(idade_texto)}") # Vai mostrar <class 'str'>
 ```

Se você executar o código acima e digitar `30` quando pedir a idade, a variável `idade_texto` conterá a string `"30"`, e não o número inteiro `30`. Isso é crucial para o próximo tópico.

## Conversão de Tipos (Type Casting)

Como vimos, `input()` retorna strings. Se precisarmos realizar operações matemáticas com um número que o usuário digitou, precisamos primeiro **converter** essa string para um tipo numérico (`int` ou `float`). Esse processo de converter um valor de um tipo para outro é chamado de **Type Casting** ou **Conversão de Tipos**.

Usamos funções com o mesmo nome dos tipos para fazer a conversão:

* `int(valor)`: Tenta converter `valor` para inteiro.
* `float(valor)`: Tenta converter `valor` para ponto flutuante.
* `str(valor)`: Converte `valor` para string.
* `bool(valor)`: Converte `valor` para booleano (lembrando das regras de `True`/`False`).

 ```python
idade_str = input("Qual sua idade? ") # Ex: usuário digita "30"

# Tentando somar diretamente (vai dar erro!)
# print(idade_str + 5) # Erro! Não pode somar string com int

# Convertendo a string para inteiro
idade_int = int(idade_str)
print(f"Daqui a 5 anos, você terá {idade_int + 5} anos.")

# Convertendo input para float
altura_str = input("Qual sua altura em metros (ex: 1.75)? ") # Ex: usuário digita "1.75"
altura_float = float(altura_str)
print(f"Sua altura é {altura_float}m.")

# Convertendo número para string (útil se não usar f-strings)
numero_sorte = 7
mensagem = "Seu número da sorte é: " + str(numero_sorte) # Converte int para str
print(mensagem)

# Convertendo número para booleano
print(bool(idade_int)) # Se idade_int for > 0, será True
 ```

**Cuidado com Erros:** Se você tentar converter uma string que não representa um número válido para `int()` ou `float()`, o Python gerará um erro chamado `ValueError`.

 ```python
texto_invalido = "abc"
# numero = int(texto_invalido) # Isso causará um ValueError!

numero_decimal_str = "10.5"
# numero_inteiro = int(numero_decimal_str) # Isso também causa ValueError! int() não converte string com ponto decimal.
numero_float = float(numero_decimal_str) # Isso funciona! (10.5)
 ```
Veremos como lidar com esses erros de forma elegante no Capítulo 9 (Tratamento de Exceções). Por enquanto, assuma que o usuário digitará valores válidos quando pedido.

## Verificando Tipos com `type()`

Relembrando: a qualquer momento, se você tiver dúvida sobre o tipo de dado armazenado em uma variável, use a função `type()`.

 ```python
x = 10
y = "10"
z = 10.0

print(type(x)) # <class 'int'>
print(type(y)) # <class 'str'>
print(type(z)) # <class 'float'>
 ```

## Resumo do Capítulo

Neste capítulo, cobrimos os fundamentos essenciais para manipular dados em Python:

* **Comentários (`#`):** Para explicar seu código.
* **Variáveis:** Nomes que guardam valores usando o operador de atribuição (`=`). Siga as regras e convenções de nomenclatura (snake_case).
* **Tipos Primitivos:**
    * `int`: Números inteiros.
    * `float`: Números com ponto decimal.
    * `str`: Sequências de texto (strings). Vimos concatenação (`+`), repetição (`*`), tamanho (`len()`) e f-strings para formatação.
    * `bool`: Valores lógicos `True` e `False`.
* **Operadores Aritméticos:** `+`, `-`, `*`, `/`, `//`, `%`, `**`. Lembre-se da ordem de precedência e use parênteses.
* **Entrada do Usuário (`input()`):** Sempre retorna uma string.
* **Conversão de Tipos (`int()`, `float()`, `str()`, `bool()`):** Essencial para converter dados (especialmente de `input()`) para o tipo necessário.
* **Verificação de Tipo (`type()`):** Para descobrir o tipo de um valor ou variável.

Com essas ferramentas, você já pode começar a escrever programas que leem dados, fazem cálculos simples e exibem resultados!

## Exercícios Práticos

Tente resolver estes exercícios para praticar os conceitos:

1.  **Calculadora Simples:** Peça ao usuário para digitar dois números. Converta-os para `float`. Calcule e imprima a soma, subtração, multiplicação e divisão dos dois números. Use f-strings para exibir os resultados de forma clara (ex: "A soma de X e Y é Z").
2.  **Mensagem de Boas-Vindas:** Peça ao usuário o nome e a idade. Converta a idade para `int`. Imprima uma mensagem de boas-vindas personalizada usando f-string, incluindo o nome e a idade (ex: "Bem-vindo(a), [Nome]! Você tem [Idade] anos.").
3.  **Repetidor de Palavras:** Peça ao usuário uma palavra e um número inteiro. Imprima a palavra repetida o número de vezes informado, separada por espaços. (Ex: Palavra="Lua", Número=3 -> Saída: "Lua Lua Lua ")
4.  **Divisão e Resto:** Peça ao usuário dois números inteiros. Calcule e imprima o resultado da divisão inteira (`//`) e o resto da divisão (`%`) entre eles. Explique o que cada resultado significa em uma frase (ex: "A divisão inteira de A por B é Q, e o resto é R.").
5.  **Verificador de Tipo:** Crie variáveis com um valor inteiro, um float, uma string e um booleano. Use a função `print()` e `type()` para exibir o valor e o tipo de cada variável.
