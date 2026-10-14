# Conceitos fundamentais de Python

**Fonte:** Estudonauta, com o professor Gustavo Guanabara (curso de Python)
**Data:** 07/10/2026

## Variáveis e tipos primitivos

Uma variável é um nome que guarda um valor na memória do computador, para ser usado depois. Em Python, o tipo da variável é definido pelo valor que ela guarda (tipagem dinâmica, sem precisar declarar o tipo antes). Python também é fortemente tipado: não mistura tipos sem conversão. Por exemplo, `"10" + 5` gera erro.

- `str` (*string*, "cadeia de caracteres"): texto entre aspas simples ou duplas (`"Olá"`, `'Python'`).
- `int` (*integer*, "inteiro"): número sem casa decimal (`10`, `-5`, `0`).
- `float` (*floating point*, "ponto flutuante"): número com casa decimal, escrita com ponto (`15.5`, `3.14`).
- `bool` (*boolean*, "booleano"): valor lógico, `True` (verdadeiro) ou `False` (falso).

### Conversão de tipos

- `int("10")` converte o texto `"10"` no número inteiro `10`.
- `str(100)` converte o número `100` no texto `"100"`.

## Operadores aritméticos

| Operador | Significado | Exemplo |
| :---: | :--- | :--- |
| `+` | Adição / concatenação (juntar textos) | `5 + 2` (7) ou `'A' + 'B'` ('AB') |
| `-` | Subtração | `5 - 2` (3) |
| `*` | Multiplicação / repetição | `5 * 2` (10) ou `'=' * 5` ('=====') |
| `/` | Divisão (o resultado é sempre `float`) | `5 / 2` (2.5) |
| `//` | Divisão inteira (arredonda para baixo) | `5 // 2` (2) |
| `%` | Módulo (resto da divisão) | `5 % 2` (1) |
| `**` | Potenciação | `5 ** 2` (25) |

## Estruturas condicionais

Permitem que o código tome caminhos diferentes conforme uma condição seja verdadeira ou falsa. Os comandos são `if` (se), `elif` (contração de *else if*, "senão se") e `else` (senão).

```python
idade = 18

if idade >= 18:
    print("Acesso permitido.")
else:
    print("Acesso negado.")
```

O operador `>=` compara se o valor da esquerda é maior ou igual ao da direita.

## Estruturas de repetição

Uma estrutura de repetição (também chamada de laço, ou *loop*, "volta") executa um bloco de código várias vezes.

### `for` (repetição com limite definido)

O `for` (*para*) percorre uma sequência, item por item, como uma lista ou um intervalo de números. Cada volta é uma iteração.

```python
for i in range(5):
    print(f"Executando passo {i}")
```

`range(5)` gera os números de 0 a 4 (o 5 fica de fora), então o bloco roda 5 vezes, com `i` valendo um número diferente a cada volta. O `f` antes das aspas (de *formatted*, "formatada") permite colocar o valor de uma variável dentro do texto, entre chaves.

### `while` (repetição baseada em condição)

O `while` (*enquanto*) executa o bloco enquanto a condição for verdadeira. Se a condição nunca ficar falsa, o laço nunca termina (laço infinito), então é preciso garantir que algo dentro do bloco a altere.

```python
contador = 0

while contador < 3:
    print(f"Contagem: {contador}")
    contador += 1
```

O `contador += 1` soma 1 ao valor atual do `contador`. É isso que faz a condição `contador < 3` ficar falsa na quarta checagem, e o laço terminar.