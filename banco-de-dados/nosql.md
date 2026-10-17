# NoSQL e o modelo BASE

Data: 15/10/2026 | Fonte: Faculdade ADS

O NoSQL (*Not Only SQL*, "não somente SQL") e suas quatro famílias já foram apresentados em [[banco-de-dados/modelos-de-dados|modelos de dados]]. Aqui está o contexto que levou a esse paradigma e como ele se organiza.

## Big Data e as limitações do modelo relacional

Big Data ("grandes dados") designa o tratamento de volumes massivos de dados, em alta velocidade e com grande variedade. Nesse cenário, os bancos relacionais enfrentam gargalos:

- **Custo de normalização e de junções (*JOINs*):** a [[normalizacao|normalização]] espalha os dados em várias tabelas, e juntá-las, quando são gigantes e há bloqueios (*locks*) sobre os dados, prejudica o desempenho.
- **Rigidez do modelo [[acid|ACID]]:** garantir de forma estrita atomicidade, consistência, isolamento e durabilidade exige muito poder de processamento. O ACID descreve transações que acontecem por inteiro ou não acontecem, levam o banco de um estado válido a outro, não interferem entre si e não se perdem depois de confirmadas.
- **Escalabilidade vertical (*scale-up*, "escalar para cima"):** os bancos relacionais pedem servidores centrais cada vez maiores. A escalabilidade horizontal (*scale-out*, "escalar para fora"), em clusters (conjuntos de máquinas trabalhando juntas) de baixo custo, é complexa nesse modelo. Os [[banco-de-dados/arquitetura-de-sgbd|bancos distribuídos]] mostram o outro lado dessa moeda.

## O modelo BASE (alternativa ao ACID)

- **BA (*Basically Available*, "basicamente disponível"):** o sistema prioriza estar sempre disponível para leitura e escrita.
- **S (*Soft State*, "estado suave"):** o estado dos dados pode mudar com o tempo, por causa da replicação feita em segundo plano.
- **E (*Eventual Consistency*, "consistência eventual"):** abre mão da consistência imediata em favor do desempenho. Os dados se tornam consistentes em algum momento futuro.

Esse compromisso decorre do [[banco-de-dados/teorema-cap|teorema CAP]].

## Comparativo: SQL x NoSQL

| Característica | Relacional (SQL) | NoSQL |
| :--- | :--- | :--- |
| Estrutura de dados | Tabelas estritas, com linhas, colunas e relacionamentos. | Chave-valor, documentos (JSON), colunas ou grafos. |
| Esquema (*schema*, a estrutura prévia dos dados) | Rígido: definido antes e imposto pelo SGBD. | Flexível ou ausente (*schema-free*). |
| Garantia transacional | ACID: foco em consistência e integridade. | BASE: foco em disponibilidade e consistência eventual. |
| Escalabilidade | Predominantemente vertical (*scale-up*, servidor maior). | Predominantemente horizontal (*scale-out*, mais nós). |
| Linguagem de acesso | SQL (`SELECT`, `JOIN`). | APIs de objetos, bibliotecas ou chaves de partição. |
| Concorrência e distribuição | Uso de *locks* na concorrência; *sharding* manual é difícil. | Tende a evitar *locks*; suporte nativo a *sharding* e replicação. |

*Sharding* é a divisão dos dados em partes distribuídas entre vários nós. Replicação é a manutenção de cópias dos dados em mais de um nó.

## Mecanismos internos

- **Map/Reduce ("mapear/reduzir"):** problemas massivos são divididos em subtarefas distribuídas a vários nós (*Map*), e os resultados são depois agregados (*Reduce*).
- **Consistent Hashing ("hash consistente"):** técnica que decide em qual nó cada dado fica, de modo que adicionar ou remover nós do cluster não exija migrar grande parte dos dados.
- **MVCC (*Multiversion Concurrency Control*, "controle de concorrência multiversão"):** permite leituras e escritas simultâneas criando versões temporárias do dado, o que reduz a necessidade de bloqueios (*locks*).
- **Vector Clocks ("relógios vetoriais"):** registram a ordem cronológica dos eventos na rede, para resolver conflitos entre versões de um mesmo dado.