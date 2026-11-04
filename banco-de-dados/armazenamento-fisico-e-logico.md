# Armazenamento físico e lógico

Data: 04/11/2026 | Fonte: Faculdade ADS

Descreve como o SGBD organiza o espaço onde guarda os dados. Corresponde ao nível interno da [[banco-de-dados/arquitetura-de-sgbd|arquitetura de três esquemas]] e é o território do gerenciador de dados armazenados. A terminologia abaixo é a usada no Oracle.

## Hierarquia de armazenamento

- **Tablespace ("espaço de tabelas", lógico):** espaço lógico delimitado dentro do banco. Exemplos: `SYSTEM`, `USERS`, `TEMPORARY` e `UNDO`.
- **Datafile ("arquivo de dados", físico):** arquivo em disco associado a um tablespace.
- **Segmento:** representa um objeto do banco, como dados, índice ou área temporária.
- **Extensão (*extent*):** conjunto de blocos contíguos alocados a um segmento.
- **Bloco:** a menor unidade de armazenamento do banco de dados.

## Modos de gerenciamento de extensões

- **Dictionary (dicionário):** o controle das extensões é feito de forma centralizada, nas tabelas do dicionário de dados. Gera maior *overhead* (sobrecarga).
- **Local:** o controle é feito no cabeçalho dos arquivos de dados do tablespace, por meio de mapas de bits (*bitmaps*). Pode ter tamanho uniforme (`UNIFORM SIZE`) ou automático (`AUTOALLOCATE`).