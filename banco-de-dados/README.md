# Aprofundamento Autônomo: Persistência e Ecossistema de Dados

Data: 26/09/2026 | Fonte: Curiosidade durante estudo na Faculdade ADS — exploração superficial com IA

**Nível de domínio: Conceitual / Panorâmico.** As seções abaixo representam o mapeamento de termos e tecnologias para criar pontes de conhecimento, sem a intenção de demonstrar domínio prático avançado — servem para reconhecer o termo quando ele aparecer, não para defendê-lo em profundidade.

## Persistência de Dados em Componentes

Dizer que um componente "não tem estado persistente" (lembrando o que já vimos em [[cbse]]) significa que ele não guarda dados de negócio na sua própria memória durante ou após a execução.

O banco de dados atua como um componente de infraestrutura/serviço responsável por gravar e manter as informações permanentemente em disco. Pode ser uma biblioteca embutida, compilada dentro do próprio programa (ex.: SQLite), ou um serviço executável separado, acessado via drivers/APIs (ex.: PostgreSQL, MySQL).

## Mapeamento panorâmico: SQL x NoSQL

- **SQL (Structured Query Language — Linguagem de Consulta Estruturada):** armazena dados em tabelas relacionais, com linhas e colunas interligadas por chaves. É o padrão tradicional, focado em integridade de dados e transações seguras. Exemplos: PostgreSQL, MySQL, SQL Server, Oracle, SQLite.
- **NoSQL (Not Only SQL — Não Somente SQL):** armazena dados em estruturas flexíveis (documentos JSON, chave-valor, grafos). Foi criado para responder a altos volumes de dados, alta velocidade de escrita/leitura e esquemas dinâmicos. Exemplos: MongoDB (documentos), Redis (chave-valor na memória RAM).

## Entendendo o ecossistema Oracle

Oracle Corporation é a gigante de tecnologia dona da linguagem Java e do banco MySQL. O Oracle Database é o seu banco relacional comercial topo de linha — são a mesma empresa, mas dois produtos de banco de dados distintos e concorrentes entre si.

É o banco padrão em bancos, multinacionais e governos, devido a tecnologias de altíssima disponibilidade e redundância (ex.: Oracle RAC), onde qualquer segundo de parada gera prejuízos milionários. Por isso exige profissionais dedicados (DBAs Oracle), devido às milhares de variáveis de ajuste de desempenho (tuning) e ao uso da linguagem de programação interna PL/SQL.

## Mapeamento de fronteiras de atuação

**Desenvolvedor de Software (escopo essencial):** modelagem básica de dados, criação de tabelas (`CREATE TABLE`) e chaves (`PRIMARY KEY`, `FOREIGN KEY`); escrita de consultas e cruzamento de dados (`SELECT`, `JOIN`, `GROUP BY`); manipulação de registros (`INSERT`, `UPDATE`, `DELETE`) e controle de transações.

**DBA — Database Administrator (fronteira avançada):** instalação, configuração e otimização do servidor do banco (tuning); gestão de segurança, privilégios de acesso, rotinas de backup, restauração e alta disponibilidade.

**Engenheiro de Dados / BI (fronteira avançada):** construção de pipelines de movimentação em massa de dados entre múltiplos sistemas (processos ETL: Extract, Transform, Load — Extrair, Transformar, Carregar); estruturação de Data Warehouses e Data Lakes para geração de relatórios executivos e análise estratégica de negócios.

---

## Nova entrada — 07/10/2026 | Fonte: Faculdade ADS

## Pilares iniciais

- **Banco de dados:** coleção organizada de dados relacionados, que representam aspectos do mundo real.
- **Minimundo (universo de discurso):** parte específica da realidade selecionada para ser gerenciada pelo sistema. Exemplo: os clientes, veículos e serviços de uma oficina mecânica.
- **SGBD (Sistema Gerenciador de Banco de Dados):** software responsável pela definição, construção, manipulação, segurança e controle de acesso aos dados.

A modelagem do minimundo corresponde ao projeto de banco de dados, uma das atividades da fase de [[diagramas-uml|projeto de software]]. Os níveis dessa modelagem estão em [[banco-de-dados/modelos-de-dados|modelos de dados]], e a forma como o SGBD se organiza por dentro está em [[banco-de-dados/arquitetura-de-sgbd|arquitetura de SGBD]].

## SGBDs do mercado

| SGBD | Tipo | Aplicação principal |
| :--- | :--- | :--- |
| PostgreSQL | Relacional (código aberto) | Projetos corporativos e engenharia de dados |
| MySQL / MariaDB | Relacional (código aberto) | Aplicações web, e-commerce, sites de conteúdo |
| Oracle Database | Relacional (proprietário) | Grandes corporações e setor financeiro |
| SQL Server | Relacional (proprietário) | Ecossistemas corporativos e de nuvem do mesmo fornecedor |
| SQLite | Relacional (*embedded*, embutido) | Aplicações móveis (Android/iOS) e desktop locais |
| MongoDB | NoSQL (documentos) | Aplicações web modernas e APIs flexíveis |
| Redis | NoSQL (chave-valor) | Cache (armazenamento temporário de alta velocidade) e sessões |
| Neo4j | NoSQL (grafos) | Redes sociais, sistemas de recomendação e detecção de fraudes |

## Papéis no ambiente de banco de dados

Complementando as fronteiras de atuação já registradas acima:

- **DBA (Database Administrator, administrador de banco de dados):** responsável pela infraestrutura, backups, recuperação, concessão de [[autenticacao-autorizacao|permissões de acesso]], segurança e *tuning* (ajuste fino de desempenho).
- **Projetista (Database Designer):** mapeia o minimundo e cria os modelos conceitual e lógico.
- **Desenvolvedor:** escreve o código da aplicação que realiza consultas e atualizações no banco.
- **Usuário casual:** acessa o sistema eventualmente, para relatórios e análises.
- **Usuário paramétrico/habitual:** opera as tarefas rotineiras do dia a dia no sistema.