# Automação de tarefas com Python

**Fonte:** Hashtag Programação, com o professor João Paulo Lira (curso de Python)
**Data:** 28/09/2026

Automatizar uma tarefa é fazer um programa executar, no lugar de uma pessoa, um trabalho manual e repetitivo. Um programa que faz isso sozinho é chamado de bot (robô, de *robot*).

Um exemplo é o cadastro de produtos de uma loja no site da própria loja. Manualmente, alguém teria que entrar no site e cadastrar os produtos um por um. Com Python, um bot pode fazer esse trabalho no lugar da pessoa.

## Do problema do mundo real ao programa

Uma dificuldade comum, principalmente no início da carreira de programação, não é escrever o código, é traduzir o pedido do mundo real em um programa. Muitas vezes o pedido nem fala em programa: apenas diz que os produtos precisam estar cadastrados no site o quanto antes.

Um caminho é escrever primeiro o passo a passo do que uma pessoa faria manualmente. Esse passo a passo é o algoritmo (a sequência de passos para resolver um problema), a "receita de bolo". Em Python, cada passo pode ser escrito como comentário (linha que começa com `#`), e o código é montado embaixo de cada um. Assim o problema é quebrado em partes menores, resolvidas uma de cada vez.

Passos do exemplo do cadastro:
1. Abrir o sistema ou navegador.
2. Fazer o login.
3. Ler a base de dados com os produtos.
4. Cadastrar produto por produto.
5. Tratar as lacunas nos dados.

## Ferramentas

**`pyautogui`** controla mouse, teclado e tela. Atua sobre a interface gráfica do [[sistema-operacional]], sem depender de integração com o software específico.
- `click(x, y)`: clica nas coordenadas (x, y) da tela.
- `write("texto")`: digita um texto.
- `press("tecla")`: aperta uma tecla, como `"tab"` ou `"enter"`.
- `position()`: mostra a posição atual do mouse, para descobrir as coordenadas.

**Tempo de espera:** sistemas demoram para carregar, e um clique antes da hora quebra a automação.
- `pyautogui.PAUSE = 1` define uma pausa (em segundos) entre todos os comandos do `pyautogui`.
- `time.sleep(segundos)` faz uma pausa pontual no código.

**`pandas`** lê a base de dados (`.csv` ou `.xlsx`). O `pd.isna` permite checar se uma coluna opcional está vazia antes de cadastrar cada linha.

## Percepção própria

Eu não sabia que bibliotecas como `pyautogui` e `pandas` eram tão simples de usar. Percebi que o difícil não é a biblioteca, é traduzir o problema do mundo real para a programação e escolher a ferramenta certa para resolvê-lo.