# Análise e desenvolvimento de sistemas


## Lógica de programação

é a habilidade de organizar pensamentos de forma estruturada para que um computador consiga resolver um problema. Computadores precisam de instruções exatas, passo a passo, chamadas de algoritmos.

## Os pilares fundamentais

Para começar a praticar, você precisa entender quatro conceitos básicos:
 
**Variáveis:** Espaços na memória para guardar dados (ex: idade = 25 ou nome = “Ana”)
 
**Estruturas Condicionais:** Decisões que o código tima (ex: Se a idade for maior que 18, permita a entrada; Senão, bloqueie).
 
**Laços de repetição (loops):** Instruções que se repetem enquanto uma condição for verdadeira (ex: Envie este email para todos os 100 clientes da lista).

 **Funções:** Bloco de código que executam uma tarefa específica e podem ser reutilizados para evitar repetição.


# Meus Primeiros Passos na Programação 🚀

## Parte 1: Entendendo as Variáveis (A Gaveta da Memória)
Imagine que a memória do seu celular é um armário cheio de gavetas. Uma variável é o ato de colar uma etiqueta em uma dessas gavetas e colocar algo dentro.

Quando você escreve:

```python
nome_usuario = "Carlos"
idade = 20
altura = 1.75
```

Você acabou de criar três gavetas. O computador agora sabe o nome, a idade e a altura do usuário.

> **Nota importante:** Textos sempre ficam entre aspas `" "`, e números quebrados usam ponto `.` em vez de vírgula.

---

## Parte 2: O Próximo Passo Prático (Tomando Decisões)
Um sistema só é "inteligente" porque ele sabe analisar as variáveis e tomar caminhos diferentes. Na programação, fazemos isso com o comando `if` (Se) e `else` (Senão).

Imagine que você está criando o sistema de login da faculdade de ADS. Se o aluno digitar a senha certa, ele entra; se digitar errado, o sistema bloqueia.

Veja como esse código é escrito de forma simples:

```python
# 1. Criamos as variáveis com os dados 
senha_correta = "ads123"
senha_digitada = "ads123" 

# 2. O sistema toma a decisão baseada na lógica
if senha_digitada == senha_correta:
    print("Acesso permitido! Bem-vindo ao portal de ADS.")
else:
    print("Senha incorreta. Acesso negado!")
```

### O que significa o `==`?
Na programação, um `=` sozinho serve para **guardar** algo na gaveta. Dois `==` servem para **comparar** se duas coisas são exatamente iguais.

PARTE 3: DEIXANDO O SISTEMA INTERATIVO (INPUT)

No código anterior, as variáveis já estavam fixas com os valores "ads123". Mas, em um sistema real, o usuário digita a senha pelo teclado na hora.

Para fazer o programa perguntar algo para você digitar, usamos o comando input() (que significa "entrada").

Vamos atualizar o código no Pydroid 3 para que ele vire um sistema real:

```python
senha_correta = "ads123"

# O computador vai exibir a pergunta e esperar você digitar no teclado
senha_digitada = input("Digite a sua senha do portal: ")

if senha_digitada == senha_correta:
    print("Acesso permitido! Bem-vindo ao portal de ADS.")
else:
    print("Senha incorreta. Acesso negado!")
```

---

PARTE 4: O QUE É UM LAÇO DE REPETIÇÃO?

Imagine que, no sistema de login que criamos, o usuário erre a senha. Do jeito que o código está hoje, o programa simplesmente fecha. Para tentar de novo, o usuário teria que abrir o aplicativo do zero. Não é assim que os sistemas reais funcionam.

Na programação, usamos o while (que significa "enquanto"). Ele diz ao computador: “Fique repetindo esse bloco de código enquanto a condição for verdadeira”.

O Código de Login Interativo e Infinito
Vamos atualizar o código no Pydroid 3. Preste atenção em como o while cria uma “escadinha” de espaços (indentação):

```python
senha_correta = "ads123"

# Criamos uma variável para controlar o laço de repetição
usuario_logado = False

# ENQUANTO o usuário NÃO estiver logado, repita tudo o que está abaixo:
while usuario_logado == False:
    senha_digitada = input("Digite a sua senha do portal: ")

    if senha_digitada == senha_correta:
        print("Acesso permitido! Bem-vindo ao portal de ADS.")
        usuario_logado = True   # Isso quebra o ciclo e o programa encerra
    else:
        print("Senha incorreta. Tente novamente.\n")
```

Nota sobre pular linhas: No final do código, usar o "\n" (barra invertida) faz com que o programa pule uma linha para a próxima tentativa. Caso prefira não usar a contrabarra, você pode usar um print() vazio na linha de baixo, que ele irá pular uma linha também.

Exemplo:
```python
else:
    print("Senha incorreta. Tente novamente.")
    print()
```

---

PARTE 5: CRIANDO UM LIMITE DE 3 TENTATIVAS (CONTADORES)

Para colocarmos o limite de 3 tentativas, precisamos apresentar um novo conceito à lógica: os Contadores. Um contador é apenas uma variável que começa em 0 e, a cada vez que o usuário erra a senha, nós somamos 1 nela. Quando esse número chegar a 3, o sistema bloqueia e encerra o programa.

O CÓDIGO COM LIMITE DE TENTATIVAS
Preste atenção na linha do while (ela tem duas condições usando a palavra and, que significa “e”):

```python
senha_correta = "ads123"
usuario_logado = False
tentativas = 0 # Começamos com zero erros

# O loop roda ENQUANTO o usuário estiver deslogado E as tentativas forem menores que 3:
while usuario_logado == False and tentativas < 3:
    senha_digitada = input("Digite a sua senha do portal: ")

    if senha_digitada == senha_correta:
        print("Acesso permitido! Bem-vindo ao portal de ADS.")
        usuario_logado = True
    else:
        tentativas = tentativas + 1 # Soma mais 1 erro na gaveta
        print("Senha incorreta!")
        print()  # Truque se não tiver a contrabarra

# Atenção: esta parte fica FORA do while (encostada na esquerda)
# Se o loop acabou e o usuário NÃO conseguiu logar, significa que ele errou as 3 vezes
if usuario_logado == False:
    print("Conta bloqueada por excesso de tentativas!")
```
