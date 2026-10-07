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