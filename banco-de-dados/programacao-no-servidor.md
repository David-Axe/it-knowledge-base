# Programação no servidor: procedures, functions e triggers

Data: 31/10/2026 | Fonte: Faculdade ADS

A programação centrada em dados consiste em colocar parte da lógica de negócio dentro do próprio servidor de banco de dados. Pode ser mais eficiente do que fazê-la na camada de aplicação, porque reduz o tráfego de dados entre as duas. As rotinas encapsulam lógica complexa e podem ser chamadas por outras rotinas ou por instruções [[banco-de-dados/sql|SQL]].

## Procedures (procedimentos)

São objetos criados com `CREATE PROCEDURE` que reúnem um conjunto de instruções SQL e lógica de programação.

- **Execução:** são chamadas com a instrução `CALL` ("chamar"), em vários SGBDs.
- **Características:** podem receber parâmetros de entrada, de saída ou de entrada e saída, executar instruções e retornar múltiplos conjuntos de resultados.

## Functions (funções)

Estabelecem uma relação entre valores de entrada e um resultado calculado, e são chamadas dentro de instruções SQL, como em cláusulas `SELECT` ou `WHERE`.

- **Funções escalares:** retornam um único valor e encapsulam operações ou cálculos complexos.
- **Funções de tabela:** retornam um conjunto de linhas e colunas (uma tabela virtual) e podem ser usadas na cláusula `FROM`.

**Diferença principal:** a procedure executa tarefas operacionais em geral, enquanto a function faz um processamento e retorna obrigatoriamente um valor, aproveitável dentro de consultas.

## Triggers (gatilhos)

São blocos de código executados automaticamente pelo SGBD em resposta a eventos de modificação de dados (`INSERT`, `UPDATE` ou `DELETE`) em tabelas ou visões.

- **Momento de acionamento:** definido por `BEFORE` (antes) ou `AFTER` (depois) da instrução.
- **Frequência de execução:** pode ser por linha (`FOR EACH ROW`, "para cada linha") ou por instrução (`FOR EACH STATEMENT`, "para cada instrução"). O suporte a cada modo depende do SGBD.