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
    * Importante: Ou o bloco do `if` é executado, ou o bloco do `else` é executado, mas **nunca ambos**`.

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

**Exemplo com `and` (Revisado):**
Para ter acesso a uma área restrita de um evento online, um usuário precisa ser assinante premium **E** ter um código de acesso especial.
 ```python
assinante_premium_str = input("Você é assinante premium? (sim/nao): ").lower()
codigo_acesso_str = input("Você possui o código de acesso especial? (sim/nao): ").lower()

eh_premium = assinante_premium_str == "sim"
tem_codigo = codigo_acesso_str == "sim"

if eh_premium and tem_codigo:
    print("Acesso à área restrita concedido! Aproveite o conteúdo exclusivo.")
else:
    print("Desculpe, acesso negado à área restrita.")
    if not eh_premium:
        print("Motivo: Assinatura premium não detectada.")
    if not tem_codigo:
        print("Motivo: Código de acesso especial não fornecido ou inválido.")
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
Você pode obter um desconto na loja se for estudante **OU** se for seu aniversário.
 ```python
estudante_str = input("Você é estudante? (sim/nao): ").lower()
aniversario_str = input("Hoje é seu aniversário? (sim/nao): ").lower()

eh_estudante = estudante_str == "sim"
eh_aniversario = aniversario_str == "sim"

if eh_estudante or eh_aniversario:
    print("Parabéns! Você tem direito a um desconto.")
else:
    print("Nenhum desconto aplicável no momento.")
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

# Exemplo: Para entrar na festa, precisa (ter convite OU estar na lista VIP) E ser maior de 18.
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

if idade < 12: # Crianças
    preco_ingresso = 8.00
    print(f"Ingresso infantil: R${preco_ingresso:.2f}")
elif idade >= 12 and idade < 60: # Jovens e Adultos
    if estudante_str == "sim":
        preco_ingresso = 10.00
        print(f"Ingresso estudante: R${preco_ingresso:.2f}")
    else:
        preco_ingresso = 20.00
        print(f"Ingresso normal: R${preco_ingresso:.2f}")
else: # Maiores de 60 (Idosos)
    preco_ingresso = 7.50
    print(f"Ingresso sênior: R${preco_ingresso:.2f}")
 ```
No exemplo acima, a verificação se é estudante (e o respectivo preço) só acontece se a pessoa tiver entre 12 e 59 anos.

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
#     status_idade = "Maior de idade"
# else:
#     status_idade = "Menor de idade"

# Usando expressão condicional (ternário)
status_idade = "Maior de idade" if idade >= 18 else "Menor de idade"

print(status_idade) # Saída: Maior de idade

pontuacao = 75
mensagem_bonus = "Bônus!" if pontuacao > 90 else "Sem bônus."
print(mensagem_bonus) # Saída: Sem bônus.
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

1.  **Verificador de Positividade:** Peça ao usuário para digitar um número. Se o número for maior que zero, imprima "Este número é positivo!". (Use um `if` simples).
2.  **Desconto Sênior:** Peça a idade do usuário. Se a idade for 60 anos ou mais, imprima "Você tem direito ao desconto para idosos!". Caso contrário, imprima "Você não se qualifica para o desconto para idosos no momento." (Use `if-else`).
3.  **Termômetro do Dia:** Peça ao usuário a temperatura ambiente em Celsius.
    * Se a temperatura for menor que 15, imprima "Está frio!".
    * Se a temperatura estiver entre 15 (inclusive) e 25 (inclusive), imprima "Temperatura agradável.".
    * Se a temperatura for maior que 25, imprima "Está calor!". (Use `if-elif-else`).
4.  **Bônus de Jogo:** Para desbloquear um bônus, um jogador precisa ter mais de 1000 pontos **E** estar no nível 5 ou superior. Peça ao usuário seus pontos (inteiro) e seu nível (inteiro). Imprima "Bônus desbloqueado!" se ambas as condições forem verdadeiras, ou "Requisitos para bônus não atendidos." caso contrário. (Use `if-else` com o operador `and`).
5.  **Elegibilidade para Frete Grátis:** Uma loja online oferece frete grátis se o valor total da compra for superior a R$ 100,00 **OU** se o cliente for um membro VIP. Peça ao usuário o valor da compra (`float`) e se ele é um membro VIP (peça para digitar 'sim' ou 'nao'). Imprima "Frete Grátis!" se pelo menos uma das condições for atendida, caso contrário, imprima "Custo de frete será aplicado." (Use `if-else` com o operador `or`).
6.  **Verificador de Cupom:** Pergunte ao usuário se ele possui um cupom de desconto (peça para digitar 'sim' ou 'nao'). Se ele **NÃO** possuir um cupom, imprima uma mensagem como "Procure nossos cupons na próxima compra para economizar!". Caso contrário (se ele tem o cupom), imprima "Ótimo! Não se esqueça de aplicar seu cupom no caixa." (Use `if-else` com o operador `not`).
7.  **Preço do Ingresso de Cinema:** O preço base de um ingresso é R$20,00.
    * Se for quarta-feira (dia de promoção), o ingresso custa metade do preço base (R$10,00) para **todos**.
    * Se **NÃO** for quarta-feira:
        * Crianças (menores de 12 anos) pagam 40% do preço base (R$8,00).
        * Idosos (60 anos ou mais) pagam 50% do preço base (R$10,00).
        * Os demais pagam o preço base (R$20,00).
    Peça ao usuário sua idade (inteiro) e se hoje é quarta-feira (peça para digitar 'sim' ou 'nao'). Calcule e imprima o preço final do ingresso. (Use `if-elif-else` e, possivelmente, `if` aninhado ou mais operadores lógicos).
8.  **Elegibilidade para Bolsa de Estudos:** Um aluno é elegível para uma bolsa de estudos se atender aos seguintes critérios: ter uma renda familiar mensal abaixo de R$2000,00 **E** (ter uma nota no exame de admissão acima de 700 pontos **OU** apresentar um histórico escolar considerado 'excelente'). Peça ao usuário para informar a renda familiar (`float`), a nota do exame (`int`) e se o histórico escolar é excelente (peça para digitar 'sim' ou 'nao'). Imprima "Elegível para bolsa" ou "Não elegível para bolsa". (Use operadores `and` e `or`, e possivelmente parênteses para garantir a ordem correta da lógica).
9.  **Quiz de Elementos Mágicos:** Crie um pequeno quiz para descobrir qual elemento mágico representa o usuário.
    * Pergunte: "Você prefere o dia ou a noite? (digite 'dia' ou 'noite')".
    * Pergunte: "Você se considera uma pessoa mais calma ou agitada? (digite 'calma' ou 'agitada')".
    Use `if-elif-else` para determinar o elemento:
        * Se for 'dia' E 'calma': "Você se parece com o elemento Terra! Estável e confiável."
        * Se for 'dia' E 'agitada': "Você se parece com o elemento Ar! Livre e perspicaz."
        * Se for 'noite' E 'calma': "Você se parece com o elemento Água! Intuitiva e adaptável."
        * Se for 'noite' E 'agitada': "Você se parece com o elemento Fogo! Apaixonada e enérgica."
        * Para qualquer outra combinação de respostas, imprima: "Você é uma combinação misteriosa de elementos!"
10. **Desafio do Jogo: Pedra, Papel e Tesoura!**
    Crie uma versão simples do jogo Pedra, Papel e Tesoura contra o "computador".
    1.  Defina a escolha do computador em uma variável no início do seu código. Por exemplo: `escolha_computador = "pedra"`. (Mantenha essa escolha fixa por enquanto, para simplificar).
    2.  Peça ao jogador para fazer sua escolha: "Escolha pedra, papel ou tesoura: ". Converta a entrada do jogador para letras minúsculas usando `.lower()` para facilitar as comparações.
    3.  Use estruturas `if-elif-else` (e operadores `and`/`or` se necessário) para comparar a escolha do jogador com a do computador e determinar o resultado:
        * Se as escolhas forem iguais, é um empate.
        * Lembre-se das regras de vitória:
            * Pedra ganha de Tesoura (`jogador == "pedra" and computador == "tesoura"`)
            * Tesoura ganha de Papel (`jogador == "tesoura" and computador == "papel"`)
            * Papel ganha de Pedra (`jogador == "papel" and computador == "pedra"`)
        * Em todos os outros casos onde não há empate e o jogador não ganhou, o computador ganhou.
    4.  Imprima uma mensagem clara indicando a escolha de cada um e o resultado (Ex: "Você escolheu [escolha_jogador], o computador escolheu [escolha_computador]. Você Ganhou!").
    5.  (Opcional) Adicione uma verificação no início para ver se o jogador digitou uma opção válida ('pedra', 'papel', ou 'tesoura'). Se não, imprima uma mensagem de erro.
