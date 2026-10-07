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