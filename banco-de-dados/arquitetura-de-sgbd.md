# Arquitetura de SGBD

Data: 07/10/2026 | Fonte: Faculdade ADS

A arquitetura de um SGBD pode ser vista por dois ângulos: como as máquinas e os processos se organizam fisicamente, e como os dados são representados em níveis de abstração.

## Arquiteturas físicas

- **Centralizada:** processamento e armazenamento concentrados em uma única máquina.
- **Cliente/servidor (3 camadas):**
  - Camada 1 (cliente): interface do usuário (apresentação).
  - Camada 2 (servidor de aplicação): regras de negócio e processamento principal, o que evita sobrecarregar o cliente e o banco.
  - Camada 3 (servidor de banco de dados): armazenamento, persistência e execução do SGBD.
- **Paralela:** múltiplos processadores ou máquinas compartilham memória e discos, buscando alto desempenho.
- **Distribuída:** dados fisicamente espalhados por nós conectados em rede.

## Arquitetura de três esquemas (ANSI/SPARC)

O padrão ANSI/SPARC (do *American National Standards Institute* e do *Standards Planning and Requirements Committee*) garante a independência dos dados por meio de três níveis de abstração:

1. **Nível externo (visões):** cada usuário ou aplicação enxerga apenas a fração dos dados que lhe é permitida.
2. **Nível conceitual (esquema conceitual):** estrutura global e lógica do banco, com entidades, relacionamentos e restrições, ocultando o armazenamento físico.
3. **Nível interno (esquema interno):** detalhes físicos de armazenamento, estrutura de arquivos e caminhos de acesso no disco.

---

## Nova entrada — 13/10/2026 | Fonte: Faculdade ADS

## Banco de dados centralizado x distribuído

Aprofundando as arquiteturas físicas já registradas acima.

**Banco de dados centralizado:** todo o SGBD, o processamento e o banco de dados físico ficam em um único servidor central (*host*, ou "hospedeiro", ou um mainframe, computador de grande porte).

- *Vantagens:* facilidade de controle pela equipe de TI, backup simplificado, ausência de duplicidade de dados e alta consistência.
- *Desvantagem:* é um ponto único de falha (*Single Point of Failure*, SPOF). Se o servidor central cai, o sistema inteiro fica indisponível.

**Banco de dados distribuído (SGBDD):** coleção de múltiplos bancos de dados logicamente inter-relacionados, mas fisicamente espalhados por vários nós (servidores) em uma rede.

- *Transparência:* para o usuário final, a distribuição deve ser invisível — o sistema deve parecer um único banco centralizado.
- *Tipos:* homogêneo (todos os nós usam o mesmo SGBD, o mesmo sistema operacional e o mesmo esquema físico) e heterogêneo (nós diferentes podem usar SGBDs e sistemas operacionais diferentes, como um nó com Oracle e outro com SQL Server).
- *Vantagens:* alta tolerância a falhas (se um nó cai, os outros continuam funcionando), menor latência em consultas locais e escalabilidade horizontal (*scale-out*, crescer adicionando mais máquinas).
- *Desvantagem:* alta complexidade para manter a sincronização e a consistência das réplicas dos dados em tempo real.

## Módulos internos do SGBD

Por dentro, o SGBD se organiza em módulos que atuam em duas camadas.

**Módulos superiores (entrada de comandos):**

- **Compilador DDL (*Data Definition Language*, linguagem de definição de dados):** processa instruções que definem a estrutura do banco, como `CREATE TABLE` e `ALTER TABLE`, e registra os metadados no catálogo do sistema.
- **Compilador e otimizador de consultas:** valida a sintaxe SQL e reordena as operações para encontrar o caminho mais rápido de busca dos dados no disco.
- **Pré-compilador DML (*Data Manipulation Language*, linguagem de manipulação de dados):** separa o código SQL da linguagem de programação hospedeira (como Python, Java ou C#), gerando transações compiladas.

**Módulos inferiores (execução):**

- **Processador de tempo de execução (*Runtime Processor*):** executa os planos de consulta otimizados e os comandos de transação.
- **Gerenciador de dados armazenados (*Stored Data Manager*):** faz a interface com o [[sistema-operacional|sistema operacional]], controlando as operações físicas de leitura e escrita em disco e o gerenciamento do *buffer* (área temporária) na memória RAM.
- **Catálogo do sistema / dicionário de dados:** repositório central dos metadados — tipos de dados, nomes, tamanhos, restrições e privilégios de acesso.