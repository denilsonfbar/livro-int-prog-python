# Capítulo 3: Tomando Decisões: Estruturas Condicionais

Nos capítulos anteriores, aprendemos a dar instruções sequenciais ao computador e a manipular dados. Mas o que torna os programas realmente poderosos é a capacidade de tomar **decisões** e executar diferentes ações com base em certas **condições**. Pense no seu dia a dia: *se* estiver chovendo, *então* você pega um guarda-chuva, *senão* você pode sair sem ele.

Neste capítulo, exploraremos as **estruturas condicionais** em Python, que permitem que nossos programas se comportem de maneira inteligente e dinâmica, respondendo a diferentes situações. Usaremos principalmente a instrução `if` e suas variações.

## Valores Booleanos e Expressões Booleanas (Uma Breve Revisão)

Como vimos no Capítulo 2, o tipo de dado booleano (`bool`) tem apenas dois valores possíveis: `True` (Verdadeiro) e `False` (Falso). As estruturas condicionais em Python dependem fundamentalmente desses valores.

Uma **expressão booleana** é qualquer expressão que resulta em um valor `True` ou `False`. Frequentemente, essas expressões envolvem operadores de comparação.

## Comparando Valores: Operadores de Comparação

Os operadores de comparação são usados para comparar dois valores. O resultado de uma comparação é sempre um valor booleano (`True` ou `False`).

Aqui estão os operadores de comparação em Python:

* `==` (Igual a): Verifica se dois valores são iguais.
    * Exemplo: `5 == 5` resulta em `True`; `5 == 3` resulta em `False`.
    * Cuidado: `==` (comparação) é diferente de `=` (atribuição)!
* `!=` (Diferente de): Verifica se dois valores são diferentes.
    * Exemplo: `5 != 3` resulta em `True`; `"olá" != "olá"` resulta em `False`.
* `>` (Maior que): Verifica se o valor da esquerda é maior que o da direita.
    * Exemplo: `10 > 5` resulta em `True`.
* `<` (Menor que): Verifica se o valor da esquerda é menor que o da direita.
    * Exemplo: `3 < 7` resulta em `True`.
* `>=` (Maior ou igual a): Verifica se o valor da esquerda é maior ou igual ao da direita.
    * Exemplo: `5 >= 5` resulta em `True`; `5 >= 4` resulta em `True`.
* `<=` (Menor ou igual a): Verifica se o valor da esquerda é menor ou igual ao da direita.
    * Exemplo: `4 <= 4` resulta em `True`; `4 <= 5` resulta em `True`.

Vamos ver alguns exemplos no código:
 ```python
# Exemplo com idade
idade_permitida = 18
idade_usuario_str = input("Digite sua idade: ")
idade_usuario = int(idade_usuario_str) # Convertendo para int

pode_entrar = idade_usuario >= idade_permitida
print(f"Pode entrar na festa? {pode_entrar}")

# Exemplo com número secreto
numero_secreto = 7
chute_str = input("Adivinhe o número secreto (entre 1 e 10): ")
chute = int(chute_str) # Convertendo para int

acertou = chute == numero_secreto
print(f"Você acertou o número? {acertou}")
 ```
Lembre-se que a função `input()` retorna uma string, por isso a necessidade de converter para `int()` antes de fazer comparações numéricas.

## A Decisão Mais Simples: A Estrutura `if`

A estrutura condicional mais básica é a instrução `if`. Ela permite que um bloco de código seja executado **somente se** uma determinada condição for verdadeira.

A sintaxe é:
 ```python
# if condicao_booleana:
#     # Bloco de código a ser executado
#     # se a 'condicao_booleana' for True.
#     # Note a indentação (4 espaços)!
#
# print("Esta linha executa sempre, pois está fora do bloco if.")
 ```

* **Explicação da Sintaxe:**
    * Começa com a palavra-chave `if`.
    * É seguida pela `condicao_booleana` a ser avaliada.
    * A linha do `if` termina com dois-pontos (`:`).
    * O **bloco de código** que será executado se a condição for `True` deve estar **indentado** (recuado com 4 espaços). A indentação é *crucial* em Python; é como ele sabe quais linhas de código pertencem ao bloco `if`.

**Exemplo Prático:**
 ```python
temperatura_str = input("Qual a temperatura atual em Celsius? ")
temperatura = float(temperatura_str) # Convertendo para float

if temperatura > 30.0:
    print("Está muito quente! Beba bastante água.")
    print("Considere usar roupas leves e protetor solar.")

if temperatura < 10.0:
    print("Está frio! Melhor pegar um casaco.")

print("Tenha um bom dia, independentemente da temperatura!") 
# Esta última linha sempre será executada, pois não está indentada sob nenhuma condição if.
 ```
No exemplo acima, as mensagens sobre calor só aparecem se a temperatura for maior que 30. A mensagem sobre frio só aparece se for menor que 10. A saudação final aparece sempre.

## Um Caminho Alternativo: A Estrutura `if-else`

Muitas vezes, queremos que o programa faça uma coisa se a condição for verdadeira, e *outra coisa* se a condição for falsa. Para isso, usamos a estrutura `if-else`.

A sintaxe é:
 ```python
# if condicao_booleana:
#     # Bloco de código A
#     # Executado se 'condicao_booleana' for True
# else:
#     # Bloco de código B
#     # Executado se 'condicao_booleana' for False
#
# print("Esta linha executa sempre, após o if ou o else.")
 ```

* **Explicação da Sintaxe:**
    * A parte do `if` funciona como antes.
    * A palavra-chave `else` é seguida por dois-pontos (`:`). Ela **não** tem uma condição própria, pois representa o caso contrário da condição do `if`.
    * O bloco de código sob o `else` também deve ser indentado.
    * Importante: Ou o bloco do `if` é executado, ou o bloco do `else` é executado, mas **nunca ambos**.

**Exemplo Prático:**
 ```python
idade_str = input("Digite sua idade: ")
idade = int(idade_str)

if idade >= 18:
    print("Você é maior de idade.")
else:
    print("Você é menor de idade.")
    anos_faltantes = 18 - idade
    print(f"Faltam {anos_faltantes} anos para você atingir a maioridade.")

print("Verificação de idade concluída.")
 ```

Outro exemplo clássico é verificar se um número é par ou ímpar usando o operador módulo (`%`):
 ```python
numero_str = input("Digite um número inteiro: ")
numero = int(numero_str)

if numero % 2 == 0: # Se o resto da divisão por 2 for 0, o número é par
    print(f"O número {numero} é PAR.")
else: # Caso contrário (se o resto for 1), o número é ímpar
    print(f"O número {numero} é ÍMPAR.")
 ```

## Combinando Condições: Operadores Lógicos

Às vezes, precisamos tomar decisões baseadas em *múltiplas* condições. Para isso, usamos os operadores lógicos: `and`, `or`, e `not`. Eles também resultam em valores booleanos (`True` ou `False`).

### Operador `and` (E)
O operador `and` retorna `True` somente se **ambas** as condições (à sua esquerda e à sua direita) forem verdadeiras. Se pelo menos uma delas for falsa, o resultado de `and` será `False`.

| Condição 1 | Condição 2 | Condição 1 `and` Condição 2 |
|------------|------------|-----------------------------------|
| `True`   | `True`   | `True`                        |
| `True`   | `False`  | `False`                       |
| `False`  | `True`   | `False`                       |
| `False`  | `False`  | `False`                       |

**Exemplo com `and`:**
Para uma pessoa poder dirigir, ela precisa ser maior de 18 anos **E** possuir carteira de motorista.
 ```python
idade = int(input("Qual sua idade? "))
tem_carteira_str = input("Você tem carteira de motorista? (sim/nao): ")

# Convertendo a resposta da carteira para booleano de forma simples
possui_carteira = tem_carteira_str.lower() == "sim" # .lower() converte para minúsculo

if idade >= 18 and possui_carteira:
    print("Você pode dirigir legalmente!")
else:
    print("Você NÃO pode dirigir legalmente.")
    if idade < 18:
        print("Motivo: Você é menor de idade.")
    if not possui_carteira: # Veremos o 'not' em breve
        print("Motivo: Você não possui carteira de motorista.")
 ```

### Operador `or` (OU)
O operador `or` retorna `True` se **pelo menos uma** das condições (à sua esquerda ou à sua direita) for verdadeira. Ele só retorna `False` se **ambas** as condições forem falsas.

| Condição 1 | Condição 2 | Condição 1 `or` Condição 2 |
|------------|------------|----------------------------------|
| `True`   | `True`   | `True`                       |
| `True`   | `False`  | `True`                       |
| `False`  | `True`   | `True`                       |
| `False`  | `False`  | `False`                      |

**Exemplo com `or`:**
Você pode descansar se for final de semana **OU** se for um feriado.
 ```python
dia_str = input("Hoje é final de semana? (sim/nao): ")
feriado_str = input("Hoje é feriado? (sim/nao): ")

eh_final_de_semana = dia_str.lower() == "sim"
eh_feriado = feriado_str.lower() == "sim"

if eh_final_de_semana or eh_feriado:
    print("Oba! Dia de descanso!")
else:
    print("Dia normal de trabalho ou estudo.")
 ```

### Operador `not` (NÃO)
O operador `not` é um operador unário (age sobre uma única condição) e simplesmente **inverte** o valor booleano da condição. Se a condição for `True`, `not condicao` será `False`. Se for `False`, `not condicao` será `True`.

| Condição | `not` Condição |
|----------|-----------------|
| `True`  | `False`       |
| `False` | `True`        |

**Exemplo com `not`:**
 ```python
chovendo_str = input("Está chovendo agora? (sim/nao): ")
esta_chovendo = chovendo_str.lower() == "sim"

if not esta_chovendo: # Se NÃO está chovendo
    print("Ótimo! O tempo está bom para um passeio.")
else:
    print("Melhor levar um guarda-chuva se for sair.")
 ```

**Precedência dos Operadores Lógicos:**
Assim como os operadores aritméticos, os operadores lógicos também têm uma ordem de precedência:
1.  `not` é avaliado primeiro.
2.  `and` é avaliado em seguida.
3.  `or` é avaliado por último.

Você pode (e deve!) usar parênteses `( )` para agrupar expressões e tornar a ordem de avaliação explícita e mais clara, especialmente quando mistura `and` e `or`.

 ```python
idade = 20
tem_convite = True
lista_vip = False

# Exemplo: Para entrar na festa, precisa ter convite OU estar na lista VIP, E ser maior de 18.
# A forma como está escrito abaixo pode ser ambígua sem parênteses para alguns leitores:
# if tem_convite or lista_vip and idade >= 18: (o 'and' seria avaliado primeiro)

# Com parênteses para clareza (e para garantir a lógica desejada):
if (tem_convite or lista_vip) and idade >= 18:
    print("Entrada permitida na festa!")
else:
    print("Entrada não permitida.")
 ```

## Múltiplas Escolhas: A Estrutura `if-elif-else`

E se tivermos mais de duas possibilidades? Por exemplo, se quisermos classificar a nota de um aluno como A, B, C, D ou F? Usar vários `if-else` aninhados (um dentro do outro) pode ficar confuso. Para isso, Python oferece a estrutura `if-elif-else`. A palavra-chave `elif` é uma abreviação de "else if".

A sintaxe é:
 ```python
# if condicao1:
#     # Bloco de código 1 (executado se condicao1 for True)
# elif condicao2:
#     # Bloco de código 2 (executado se condicao1 for False E condicao2 for True)
# elif condicao3:
#     # Bloco de código 3 (executado se cond1 e cond2 forem False E cond3 for True)
# # ...pode ter quantos elifs quiser...
# else:
#     # Bloco de código final (executado se NENHUMA das condições anteriores for True)
 ```

* **Fluxo de Execução:**
    * Python verifica a `condicao1`. Se for `True`, executa o Bloco 1 e **pula todo o resto` (elifs e else).
    * Se `condicao1` for `False`, ele verifica a `condicao2` do primeiro `elif`. Se `True`, executa o Bloco 2 e **pula o resto`.
    * Isso continua para cada `elif`.
    * Se **todas** as condições dos `if` e `elif`s forem `False`, o bloco do `else` (se existir) é executado.
    * Apenas **um bloco` (if, um dos elifs, ou else) será executado.

**Exemplo Prático: Menu de Opções**
 ```python
print("Bem-vindo à nossa lanchonete!")
print("Opções:")
print("1 - Hambúrguer")
print("2 - Pizza")
print("3 - Salada")
print("4 - Suco")

opcao_str = input("Digite o número da sua opção: ")

if opcao_str == "1":
    print("Você escolheu Hambúrguer! Custa R$15.00")
elif opcao_str == "2":
    print("Você escolheu Pizza! Custa R$25.00")
elif opcao_str == "3":
    print("Você escolheu Salada! Custa R$12.00")
elif opcao_str == "4":
    print("Você escolheu Suco! Custa R$8.00")
else:
    print(f"Opção '{opcao_str}' inválida. Por favor, escolha um número do menu.")
 ```

## Decisões Dentro de Decisões: Condicionais Aninhadas

É possível colocar uma estrutura `if` (ou `if-else`, `if-elif-else`) dentro de outro bloco `if`, `elif` ou `else`. Isso é chamado de **condicionais aninhadas** (ou "nested conditionals").

**Exemplo:**
 ```python
idade = int(input("Qual sua idade? "))
estudante_str = input("Você é estudante (sim/nao)? ").lower()

if idade < 18:
    print("Você tem direito a meio ingresso (menor de idade).")
elif idade >= 18 and idade <= 60:
    if estudante_str == "sim":
        print("Você tem direito a meio ingresso (estudante).")
    else:
        print("Você paga ingresso normal.")
else: # Maiores de 60
    print("Você tem direito a meio ingresso (idoso).")
 ```
No exemplo acima, a verificação se é estudante só acontece se a pessoa tiver entre 18 e 60 anos.

* **Cuidado:** Condicionais aninhadas podem tornar o código complexo e difícil de ler se houver muitos níveis. Use com moderação. Muitas vezes, uma estrutura `if-elif-else` bem planejada ou o uso de operadores lógicos pode evitar aninhamentos desnecessários.

## (Dica Avançada) Expressão Condicional (Operador Ternário)

Python oferece uma forma concisa de escrever uma atribuição `if-else` simples em uma única linha, usando a **expressão condicional** (também conhecida como operador ternário).

A sintaxe é:
`valor_se_true if condicao else valor_se_false`

**Exemplo:**
 ```python
idade = 20

# Usando if-else tradicional
# if idade >= 18:
#     status = "Maior de idade"
# else:
#     status = "Menor de idade"

# Usando expressão condicional (ternário)
status = "Maior de idade" if idade >= 18 else "Menor de idade"

print(status) # Saída: Maior de idade
 ```
Isso pode ser útil para atribuições simples, mas para lógicas mais complexas, a estrutura `if-else` tradicional é mais legível.

## Resumo do Capítulo

Neste capítulo, você aprendeu a controlar o fluxo do seu programa com base em condições:

* **Operadores de Comparação:** `==`, `!=`, `>`, `<`, `>=`, `<=` são usados para criar expressões booleanas.
* **Estrutura `if`:** Executa um bloco de código se uma condição for `True`.
* **Estrutura `if-else`:** Executa um bloco se a condição for `True` e outro bloco se for `False`.
* **Operadores Lógicos:**
    * `and`: `True` se ambas as condições forem `True`.
    * `or`: `True` se pelo menos uma condição for `True`.
    * `not`: Inverte o valor booleano de uma condição.
* **Estrutura `if-elif-else`:** Permite testar múltiplas condições em sequência e executar um bloco correspondente à primeira condição verdadeira, ou um bloco `else` se nenhuma for.
* **Indentação:** É fundamental em Python para definir os blocos de código dentro das estruturas condicionais.
* **Condicionais Aninhadas:** Permitem estruturas de decisão mais complexas, mas devem ser usadas com cautela para manter a legibilidade.
* **Expressão Condicional (Ternário):** Uma forma concisa para `if-else` simples em atribuições.

Com as estruturas condicionais, seus programas agora podem reagir de maneiras diferentes a diferentes entradas e situações!

## Exercícios Práticos

1.  **Classificador de Número:** Peça ao usuário para digitar um número. Use `if-elif-else` para imprimir se o número é "Positivo", "Negativo" ou "Zero".
2.  **Calculadora Simples Melhorada:** Peça ao usuário dois números e depois qual operação ele deseja realizar (ex: "soma", "subtracao", "multiplicacao", "divisao"). Use `if-elif-else` para realizar a operação escolhida e imprimir o resultado. Se a operação for divisão, verifique se o segundo número é zero antes de dividir; se for, imprima uma mensagem de erro apropriada (ex: "Não é possível dividir por zero.").
3.  **Verificador de Vogal ou Consoante:** Peça ao usuário para digitar uma única letra. Use `if-elif-else` e operadores lógicos para determinar se a letra é uma vogal (a, e, i, o, u - considere maiúsculas e minúsculas) ou uma consoante. Imprima o resultado.
4.  **Faixa Etária:** Peça a idade de uma pessoa. Use `if-elif-else` para classificá-la em uma das seguintes faixas: "Criança" (0-12 anos), "Adolescente" (13-17 anos), "Adulto" (18-59 anos), "Idoso" (60 anos ou mais).
5.  **Adivinhe o Animal (Simples):** Crie um mini-jogo. Pense em um animal. Faça duas perguntas de sim/não ao usuário sobre características do animal (ex: "O animal que estou pensando vive na água? (sim/nao)", "Ele tem pelos? (sim/nao)"). Com base nas respostas, tente "adivinhar" se o animal é o que você pensou usando `if-elif-else` e operadores lógicos. Se não for, diga que você não sabe qual é. (Ex: Se vive na água e não tem pelos, pode ser um peixe).