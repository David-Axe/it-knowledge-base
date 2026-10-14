# Data Warehouse e OLAP

Data: 13/10/2026 | Fonte: Faculdade ADS

Um data warehouse (armazém de dados) é um repositório de dados históricos e consolidados, organizado para consultas analíticas e apoio à decisão, em oposição ao banco operacional do dia a dia. Esse é o território do Engenheiro de Dados/BI citado em [[banco-de-dados/README|banco de dados]].

## OLTP x OLAP

- **OLTP (*Online Transaction Processing*, processamento de transações online):** voltado ao dia a dia operacional. Tem altas taxas de escrita, trabalha com dados correntes e usa tabelas altamente normalizadas, para evitar redundância.
- **OLAP (*Online Analytical Processing*, processamento analítico online):** voltado ao apoio à decisão e à *Business Intelligence* (inteligência de negócios). Trabalha com dados históricos consolidados e consultas complexas de leitura e agregação, feitas sob demanda (*ad hoc*).

## Modelo multidimensional (cubo de dados)

- **Medida (fato):** valor numérico central a ser analisado ou somado, como total de vendas, quantidade ou lucro.
- **Dimensões:** os eixos de contexto da medida, como produto, local e tempo.
- **Hierarquias de dimensão:** níveis de detalhamento dentro de uma dimensão. Exemplo: cidade → estado → país.

## Esquema estrela (*Star Schema*)

Padrão de projeto multidimensional implementado em bancos de dados relacionais ([[banco-de-dados/modelos-de-dados|modelo relacional]]), abordagem conhecida como ROLAP (*Relational OLAP*, OLAP relacional).

- **Tabela de fatos (centro):** armazena as chaves estrangeiras para as dimensões e as medidas numéricas. É altamente normalizada e de grande volume.
- **Tabelas de dimensão (pontas):** armazenam os atributos descritivos. São desnormalizadas de propósito, para evitar junções (*JOINs*) excessivas nas consultas analíticas.

## Operações OLAP

- **Roll-up (subir na hierarquia):** agrupa os dados em um nível de abstração mais alto. Exemplo: consolidar as vendas de cidades para estados.
- **Drill-down (descer na hierarquia):** operação oposta ao roll-up, que aumenta o nível de detalhe. Exemplo: detalhar as vendas de ano para meses ou dias.
- **Slice (fatiar):** seleção por igualdade em uma dimensão específica. Exemplo: filtrar apenas `estado = 'SC'`.
- **Dice (cortar em cubos):** seleção por intervalo em múltiplas dimensões. Exemplo: `estado IN ('SC', 'PR')` e `ano BETWEEN 2024 AND 2026`.
- **Pivoting (rotação):** gira os eixos de análise para apresentar os dados em formato de matriz de tabulação cruzada, no estilo de uma planilha.

## Técnicas de indexação analítica

- **Índices de mapa de bits (*Bitmap Indexes*):** usados em colunas de baixa cardinalidade (poucos valores distintos possíveis, como sexo, estado civil ou notas de 1 a 5). Substituem listas de endereços por vetores de bits (0 e 1) e usam operações binárias muito rápidas na memória (`AND`, `OR`) para responder a consultas complexas.
- **Índices de junção (*Join Indexes*):** mapeiam previamente os endereços físicos (*rids*, identificadores de linha) dos registros da tabela de fatos com os das tabelas de dimensão, acelerando a execução de junções complexas em esquemas estrela.