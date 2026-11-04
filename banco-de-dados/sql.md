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

---

## Nova entrada — 04/11/2026 | Fonte: Faculdade ADS

## Junções externas (*outer joins*)

Complementando as consultas já registradas acima. Uma junção (*join*) combina linhas de duas tabelas. Nas junções externas, as linhas sem correspondência também aparecem no resultado, com os campos ausentes preenchidos por `NULL` (valor vazio).

- **`LEFT JOIN` / `RIGHT JOIN`:** retornam as linhas combinadas mais as linhas sem correspondência da tabela da esquerda (`LEFT`) ou da direita (`RIGHT`).
- **`FULL JOIN`:** retorna todas as linhas combinadas e as não combinadas das duas tabelas. Está previsto no padrão SQL, mas nem todo SGBD o suporta nativamente (o Access, por exemplo, não). Nesses casos, ele é construído com a união (`UNION`) de um `LEFT JOIN` com um `RIGHT JOIN`.

## Consultas aninhadas (*subqueries*) e problemas de diferença

- **Consulta aninhada tipo I:** a subconsulta interna é independente. É avaliada uma única vez e não faz referência às tabelas da consulta externa. É frequente com o operador `IN` e em instruções `DELETE`.
- **Problemas de diferença ("não"):** enunciados que buscam registros presentes em uma tabela e ausentes em outra. Exemplo: "professores que não são alunos". Formulações corretas: `NOT IN` com subconsulta tipo I; `LEFT JOIN` com `WHERE ... IS NULL`; ou operadores de diferença (`EXCEPT`, ou `MINUS` em alguns SGBDs).
- **Armadilha:** a junção com desigualdade (`<>`) não resolve esses problemas. Ela devolve todos os pares de linhas diferentes, então um professor que também é aluno ainda aparece combinado com algum outro aluno.

## `WHERE` x `HAVING`

- **`WHERE` ("onde"):** filtra linhas individuais antes de qualquer agrupamento ou agregação.
- **`HAVING` ("tendo"):** filtra depois da agregação feita pelo `GROUP BY`, aplicando a condição sobre os grupos.

## Views, CTEs e funções de janela

- **Views (visões):** tabelas virtuais baseadas em um `SELECT` armazenado. Encapsulam lógica complexa, simplificam consultas e acrescentam uma camada de segurança ao ocultar colunas ou linhas sensíveis. Correspondem, na prática, ao nível externo (visões) da [[banco-de-dados/arquitetura-de-sgbd|arquitetura de três esquemas]].
- **CTEs (*Common Table Expressions*, expressões de tabela comuns):** consultas temporárias nomeadas, criadas com a cláusula `WITH`, que existem apenas durante a execução da consulta que as define. Melhoram a legibilidade ao dividir uma lógica complexa em etapas claras.
- **Funções de janela (*window functions*):** executam cálculos sobre conjuntos de linhas relacionadas, por meio de `OVER (PARTITION BY ...)`, sem reduzir o detalhamento linha a linha. Permitem comparar cada registro com a média ou o total do seu grupo.
- **Funções nativas utilitárias:** como `UPPER` (converte para maiúsculas), `REPLACE` (substitui trechos de texto) e `ROUND` (arredonda números). São diferentes das funções criadas pelo usuário, descritas em [[banco-de-dados/programacao-no-servidor|programação no servidor]].