# Modelos de Dados

Data: 07/10/2026 | Fonte: Faculdade ADS

Um modelo de dados define como as informações de um banco são organizadas e relacionadas. Ao longo do tempo surgiram vários modelos, e a modelagem de um banco passa por níveis diferentes de abstração.

## Evolução dos modelos de dados

- **Hierárquico:** estrutura em árvore, com relação de pai e filho. É rígido.
- **Rede (CODASYL, de *Conference on Data Systems Languages*):** registros com múltiplos pais, permitindo relacionamentos N:M (muitos para muitos).
- **Relacional (SQL):** padrão dominante de mercado desde a década de 1980. Os dados são organizados em tabelas (relações), compostas por linhas (tuplas) e colunas (atributos), e ligadas por chaves primárias e estrangeiras.
- **Objeto-relacional:** integração nativa com linguagens orientadas a objetos.
- **NoSQL (*Not Only SQL*, "não somente SQL"):** focado em escalabilidade e flexibilidade, dividido em quatro tipos:
  - *Chave-valor:* acesso muito rápido (ex.: Redis).
  - *Documentos:* dados em JSON/BSON (*Binary JSON*, versão binária do JSON), como no MongoDB.
  - *Família de colunas:* dados organizados em colunas, para volumes muito altos de escrita (ex.: Cassandra).
  - *Grafos:* foco em nós e conexões entre eles (ex.: Neo4j).

A comparação inicial entre SQL e NoSQL está em [[banco-de-dados/README|banco de dados]], junto com os SGBDs que implementam cada modelo.

## Níveis de abstração na modelagem

- **Modelo conceitual:** alto nível, independente de software ou SGBD. Exemplo: o Diagrama Entidade-Relacionamento.
- **Modelo representacional (lógico):** nível intermediário, já próximo do mercado. Exemplo: o modelo relacional, com tabelas e tipos de dados.
- **Modelo físico:** baixo nível, que detalha como tabelas e índices são gravados fisicamente em memória e disco.

---

## Nova entrada — 15/10/2026 | Fonte: Faculdade ADS

## As quatro famílias NoSQL em detalhe

Aprofundando as famílias já registradas acima, com funcionamento e casos de uso. O contexto do paradigma está em [[banco-de-dados/nosql|NoSQL e o modelo BASE]], e os SGBDs que as implementam estão na tabela de [[banco-de-dados/README|banco de dados]].

| Tipo | Funcionamento | Casos de uso | Exemplos |
| :--- | :--- | :--- | :--- |
| Chave-valor (*Key-Value*) | Associa uma chave única a um valor ou bloco de dados. Leitura e escrita muito rápidas (alguns, como o Redis, operam na memória RAM). | Caches de sessão, carrinhos de compras, jogos online. | Redis, Dynamo, Voldemort. |
| Documentos | Armazena dados em documentos semiestruturados (com organização interna, mas sem esquema fixo), em JSON, BSON ou XML. | Cadastros flexíveis, catálogos de e-commerce, APIs web. | MongoDB, CouchDB. |
| Família de colunas (*Column-Family*) | Organiza e armazena os dados por colunas em vez de linhas, reduzindo a E/S (entrada e saída em disco) nas consultas. | Análise de séries temporais, Big Data, logs de sistemas. | Cassandra, HBase, BigTable. |
| Grafos | Armazena dados como vértices (nós) e arestas (conexões), ambos com propriedades. | Redes sociais, sistemas de recomendação, detecção de fraudes. | Neo4j, InfoGrid. |