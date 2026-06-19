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


O CÓDIGO COMPLETO DA CALCULADORA

```python
# Criamos uma variável para controlar quando a calculadora deve fechar
continuar = True

while continuar == True:
    print("--- MENU DA CALCULADORA ---")
    print("1 - Somar")
    print("2 - Subtrair")
    print("3 - Sair")
    print()

    opcao = input("Escolha uma opcao (1, 2 ou 3): ")
    print()

    # Se o usuário quiser sair, mudamos a variável para False e o loop quebra
    if opcao == "3":
        print("Calculadora encerrada. Até logo!")
        continuar = False
        
    # Se o usuário escolher uma opção válida de conta (1 ou 2)
    elif opcao == "1" or opcao == "2":
        num1 = float(input("Digite o primeiro número: "))
        num2 = float(input("Digite o segundo número: "))
        print()

        if opcao == "1":
            resultado = num1 + num2
            print("O resultado da soma é:", resultado)
        else:
            resultado = num1 - num2
            print("O resultado da subtração é:", resultado)
            print()  # Pula linha para organizar

    # Se digitar qualquer outra coisa inválida 
    else:
        print("Opção inválida! Tente novamente.")
        print()
```

---

TRÊS NOVAS REGRAS DE LÓGICA PARA OBSERVAR:

O elif: Significa “Senão Se”. Ele serve para criar uma terceira ou quarta opção no sistema entre o if e o else.

O operador or (“ou”): Significa que o programa vai pedir os números se você escolher a opção 1 “ou” opção 2.

Conversão com float(): Repare que envolvemos o input() dentro do float(). Isso garante que o celular trate o que você digitou como número matemático, aceitando até números com ponto (ex: 10.5).

---

O projeto da calculadora serve para treinar a Arquitetura de Fluxo de Dados que move os grandes sistemas de mercado (como Uber, e-commerces e bancos).

INTERAÇÃO E CONVERSÃO DE TEXTO PARA NÚMERO 

O que foi feito: usamos float(input()) para capturar os dados do teclado.

Utilidade real: o comando input() sempre recebe tudo como se fosse texto (letras). Se o usuário digitar 20 e 30, o computador entende como duas palavras. O comando float() limpa o dado e o transforma em número matemático.

No mercado: é o que o sistema da Uber faz ao pegar a distância em um texto digitada no mapa e transformá-la em um número real para calcular o preço da sua corrida.

---

A LÓGICA DOS MENUS DE ESCOLHA

O que foi feito: Criamos opções numéricas (1 - Somar, 2 - Subtrair, 3 - Sair).

Utilidade Real: O uso do if, elif e else direciona o processador do celular para executar apenas o bloco de código que o usuário solicitou, ignorando o resto.

No mercado: É a estrutura de qualquer menu de atendimento automático (como o suporte de grandes empresas no WhatsApp) ou as categorias de filtros dentro do Mercado Livre.

---

PERSISTÊNCIA DE TELA (MANTER O APP ABERTO)

O que foi feito: Controlamos o ciclo com a variável continuar = True.

Utilidade real: Sistemas de console fecham imediatamente após exibir um resultado. O while amarra o programa em um ciclo eterno para que o usuário faça quantas contas quiser. O app só fecha de forma controlada quando o usuário escolhe a opção “Sair”.

No mercado: É o motor de qualquer app de celular. Quando você clica em “Sair da Conta” (Logout) na Netflix, o sistema roda um comando idêntico mudando o seu status para False, encerrando a sua sessão com segurança.


Listas (Array)
  Até agora, cada variável criada era como uma gaveta pequena que só guardava uma informação por vez.
  Uma Lista (que na faculdade chamamos teoricamente de Array ou Vetor) é como um armário organizador cheio de gavetas numeradas. Ela.permite guardar dezenas, centenas ou milhares de dados dentro de uma única variável. 

      Como funciona no Python (A Regra do Zero)
  No Python, criamos uma lista usando colchetes [ ].
  O computador organiza os itens dando uma “posição” (índice) para cada um, começando sempre pelo número zero (0).
*imagine uma lista de compras:

#posição:     0                       1                   2
Produtos = [“Notebook” , “Celular” , “Teclado”]



Código para aplicar no app

#Criando a lista com 3 itens
Carrinho = [“Mouse”, “Teclado” , “Monitor”]

#Exibindo a lista inteira na tela
print(“Meu carrinho de compras completo:”)
print(carrinho)
print() #Truque pula linha

#Buscando apenas UM item específico pela posição dele (índice)
print(“O primeiro item da lista é: “ , carrinho [0])
print(“O segundo item da lista é: “ , carrinho [1])


      Próximo passo adicionar itens na Lista (append)
  Em um sistema real (como o carrinho da Amazon), o usuário clica em um botão e novos produtos entram na lista dinamicamente. No Python, fazemos isso usando o comando .append() (que significa “ acrescentar “ ou “anexar”).

Vamos atualizar o código:

#Adicionando um novo produto no final da lista
carrinho.append(“fone de ouvido”)
print() #Pula linha
print(“carrinho atualizado com o novo item:”)
print(carrinho)



    Como a faculdade cobra isso?
  Na faculdade de ADS, os professores vão te mostrar que as listas são o coração de sistemas que gerenciam dados, em uma prova ou trabalho, o desafio clássico será: “Crie um sistema onde o usuário digita o nome do produto e o sistema adiciona este produto na lista automaticamente”.


Vamos criar um carrinho de compras de um e-commerce:


carrinho=[]
continuar = True

while continuar == True:
   print('--- MENU DO CARRINHO ---')
   print('1 - Adicionar Produto')
   print('2 - Ver Carrinho')
   print('3 - Fechar Pedido e Sair')
   print()
	
   opcao = input('Escolha um opção: ')
   print()
	
   if opcao == '1':
      novo_produto = input('Digite o nome do produto para o carrinho: “)
      carrinho.append(novo_produto)
      print('Produto adicionado com sucesso!')
      print()
		
  elif opcao == '2':
      print('seu carrinho atual tem estes itens:')
      print(carrinho)
      print()
  elif opcao == '3':
      print('Pedido fechado! Obrigado Por comprar conosco.')
      continuar = False
		
  else:
      print('opção inválida!')
      print()

