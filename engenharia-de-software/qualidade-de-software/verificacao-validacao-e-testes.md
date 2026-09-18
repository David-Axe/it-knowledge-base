# Verificação, Validação e Testes de Software

Data: 10/09/2026 | Fonte: Faculdade ADS

O processo de garantia da qualidade em Engenharia de Software fundamenta-se nos conceitos de Verificação e Validação (V&V). A distinção clássica estabelecida por Barry Boehm resume o propósito de cada pilar:

* **Verificação:** Avalia se o produto está sendo construído da maneira correta. Foca nos processos, especificações técnicas e artefatos intermediários para garantir que o software atenda rigorosamente às regras impostas a cada etapa.
* **Validação:** Avalia se o produto certo está sendo construído. Foca nas necessidades reais do usuário final e no ambiente operacional, garantindo que a aplicação cumpra a "missão" e os requisitos funcionais previstos.

**Abordagens de Análise (Estática vs. Dinâmica):**
* **Análise Estática:** Não exige a execução do software. Abrange a revisão de documentação, inspeção de requisitos, verificação de diagramas e leitura de código-fonte. A identificação de falhas na fase estática evita o desperdício de tempo e esforço, barateando drasticamente o custo de correção.
* **Análise Dinâmica:** Exige que o programa seja executado em ambiente controlado para monitorar seu comportamento diante de entradas e saídas reais.

**Técnicas de Projeto de Testes:**
* **Caixa-Preta (Funcional/Comportamental):** Concentra-se nos requisitos funcionais e no comportamento externo do sistema. Avalia o retorno do software para dados de entrada específicos sem analisar a estrutura interna do código.
* **Caixa-Branca (Estrutural/Caixa-de-Vidro):** Concentra-se na lógica interna do código-fonte. Elabora casos de teste para exercitar caminhos independentes, estruturas de dados, loops e condições lógicas (verdadeiro/falso). Essas técnicas se conectam diretamente com o ciclo Red-Green-Refactor documentado em [[teste-de-software]].

**Relação com QA/QC:**
Verificação e Validação não são sinônimos de QA e QC, mas há proximidade entre os conceitos. Verificação, por focar no processo e nas etapas intermediárias, se aproxima do papel mais abrangente de [[qa-qc|QA]]. Validação, por focar em confirmar que o produto atende à necessidade real do usuário, tem relação parcial com [[qa-qc|QC]] — embora não sejam idênticos: QC concentra-se em encontrar defeitos no produto já pronto, enquanto Validação é especificamente sobre confirmar que aquilo resolve o problema do usuário. Um sistema pode passar em todos os testes de QC e ainda falhar na Validação, se não for de fato o que o cliente precisava.

---

## Nova entrada — 17/09/2026 | Fonte: Faculdade ADS

## A Regra dos 10 de Myers

Proposta por Myers (1979), a Regra dos 10 estipula que o custo para identificar e corrigir um defeito multiplica-se por 10 a cada etapa que o problema avança no ciclo de vida do desenvolvimento:

Desenho → Especificação → Construção → Teste → Produção

Essa regra quantifica algo que já havia sido registrado aqui de forma qualitativa: a Análise Estática, por identificar falhas ainda na fase de requisitos e arquitetura, evita custos que crescem exponencialmente se o problema só for detectado em produção — incluindo refatorações complexas e danos à reputação da empresa.

---

## Nova entrada — 18/09/2026 | Fonte: Faculdade ADS

## Verificação e Validação — duas analogias

Duas analogias ajudam a fixar a distinção entre Verificação e Validação já registrada aqui:

- **Esqueleto x corpo em funcionamento:** a Verificação (análise estática) examina o código-fonte, a arquitetura e os requisitos sem executar o programa — é avaliar a "estrutura óssea" do software. A Validação (análise dinâmica) avalia o software em execução, com dados reais de entrada e saída — é examinar o "corpo em pleno funcionamento".
- **Planta da casa x parede estrutural pronta:** alterar uma regra ainda na fase de Verificação é como mudar a planta da casa no computador, junto com o engenheiro — barato e simples. Corrigir um erro só na Validação, ou já em produção, é como mandar derrubar uma parede estrutural pronta: gera um custo astronômico de refatoração, material e mão de obra.

## Custos da Qualidade: conformidade x não-conformidade

Complementando a Regra dos 10 de Myers já registrada aqui, os custos da qualidade se dividem em duas categorias:

- **Custos de Conformidade (investimento):** dividem-se em Prevenção (ações anteriores à codificação, como treinamento e padronização) e Avaliação (inspeções e baterias de teste antes do envio).
- **Custos de Não-Conformidade (prejuízo):** dividem-se em Falhas Internas (defeitos identificados dentro da empresa antes da entrega) e Falhas Externas (defeitos descobertos pelo cliente já em produção).

A Falha Externa é a categoria mais grave: pode gerar multas contratuais pesadas, destruir a reputação da marca e resultar em cancelamento de contratos, ao ponto de inviabilizar o negócio.