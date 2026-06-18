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
