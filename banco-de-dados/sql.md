# SQL

Data: 31/10/2026 | Fonte: Faculdade ADS

SQL (*Structured Query Language*, "linguagem de consulta estruturada") é a linguagem usada para definir, manipular e consultar dados em bancos do [[banco-de-dados/modelos-de-dados|modelo relacional]]. Os módulos do SGBD que processam essas instruções, como os compiladores DDL e DML, estão descritos em [[banco-de-dados/arquitetura-de-sgbd|arquitetura de SGBD]].

## Sublinguagens da SQL

- **DDL (*Data Definition Language*, linguagem de definição de dados):** atua sobre a estrutura e os metadados, para criar, alterar e organizar esquemas e tabelas. Exemplos: `CREATE`, `ALTER`.
- **DML (*Data Manipulation Language*, linguagem de manipulação de dados):** opera sobre os registros das tabelas. Exemplos: `INSERT`, `UPDATE`, `DELETE`.
- **DQL (*Data Query Language*, linguagem de consulta de dados):** recupera dados por meio do comando `SELECT`. Algumas classificações incluem o `SELECT` dentro da DML.

**CRUD** (*Create, Read, Update, Delete*, criar, ler, atualizar e excluir) são as quatro operações básicas sobre os dados. Correspondem a `INSERT`, `SELECT`, `UPDATE` e `DELETE`.

## Restrições de integridade (*constraints*)

São regras que o SGBD aplica para manter os dados válidos:

- **`PRIMARY KEY` (chave primária):** garante que o atributo identifique unicamente cada linha (tupla). Aplica implicitamente `NOT NULL` (não aceita valor vazio) e `UNIQUE`.
- **`UNIQUE` (único):** garante que os valores de uma coluna não se repitam, sem precisar ser a chave primária. Exemplo: campos de login.
- **`CHECK` (verificar):** aplica uma validação lógica sobre os valores de uma coluna. Exemplo: `CHECK (idade >= 18)`.

## Tipos de dados (domínios)

Definem o formato que cada coluna aceita e ajudam a otimizar o armazenamento. Exemplos: `CHAR` (texto de tamanho fixo), `VARCHAR` (texto de tamanho variável), `INT` (inteiro), `DECIMAL` (número com casas decimais) e `BOOLEAN` (verdadeiro ou falso).

## Consultas (DQL)

- **Filtros com `WHERE` ("onde"):** usam operadores relacionais (`=`, `>`, `<`, `>=`, `<=`) e lógicos (`AND`, `OR`, `NOT`) para refinar a busca.
- **Busca inexata com `LIKE` ("como") e `%`:** verifica padrões de texto em vez de correspondências exatas. O `%` representa qualquer sequência de caracteres. Exemplo: `nome LIKE 'Ma%'` encontra todos os nomes que começam com "Ma".
- **`ORDER BY` e `LIMIT`:** o `ORDER BY` ("ordenar por") organiza o resultado em ordem crescente (`ASC`) ou decrescente (`DESC`). O `LIMIT` ("limite") restringe a quantidade de registros retornados, o que é útil na paginação. Em vários SGBDs a sintaxe do limite é essa; em outros, é diferente.