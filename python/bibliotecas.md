# Bibliotecas do Python

**Fontes:** Hashtag Programação, com o professor João Paulo Lira (curso de Python); Estudonauta, com o professor Gustavo Guanabara (curso de Python)
**Data:** 28/09/2026

## O que é uma biblioteca

Uma biblioteca é um conjunto de código pronto, escrito por outras pessoas, que pode ser trazido para dentro de um programa com o comando `import` ("importar"). Em vez de reescrever do zero uma tarefa comum, como ler uma tabela ou controlar o mouse, o programador reaproveita o que já foi feito e testado.

Existem dois tipos:

- **Nativas:** já vêm com o Python, mas ainda precisam ser importadas. Também são chamadas de biblioteca padrão (*standard library*, "biblioteca padrão"). Exemplo: `time`, para controle de tempo e pausas.
- **De terceiros:** criadas por outras pessoas ou empresas e instaladas à parte. Exemplos: `pandas` e `pyautogui`.

## Exemplos

- **`pandas`:** lê e organiza bases de dados, como arquivos `.csv` e `.xlsx`, em forma de tabela (DataFrame, "quadro de dados"), e permite percorrer linha por linha e checar valores vazios.
- **`pyautogui`:** controla mouse, teclado e tela por código, simulando o que uma pessoa faria. Atua sobre a interface gráfica do [[sistema-operacional]], então funciona com qualquer programa aberto, sem depender de integração com ele. Trabalha com coordenadas (x, y) de pixels (o menor ponto da tela), contadas a partir do canto superior esquerdo.
- **`time`:** nativa. Usada para pausar o programa e esperar um sistema carregar antes do próximo comando.

No cadastro de produtos de uma loja, descrito em [[automacao-de-tarefas]], as três trabalham juntas: o `pandas` lê a lista de produtos, o `pyautogui` digita e clica no site, e o `time` dá o intervalo entre as etapas.

## Percepção própria

Eu sabia que existiam bibliotecas, mas só ao usá-las na prática percebi o quanto elas ampliam o que o Python consegue fazer, e como são simples de usar.