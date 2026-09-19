# QA (Quality Assurance) e QC (Quality Control)

**03/09/2026 — Estudo autônomo (mentoria com IA)**

QA e QC são dois termos frequentemente confundidos, mas que representam coisas diferentes dentro da área de qualidade de software.

## Conceitos principais

**QC (Quality Control / Controle de Qualidade)** é mais relativo ao profissional que pega o produto final já pronto — o software terminado — e faz todos os testes possíveis para averiguar a qualidade do produto já concluído, antes dele chegar ao cliente. É uma atividade reativa: verifica o que já foi construído.

**QA (Quality Assurance / Garantia de Qualidade)** é mais abrangente. O profissional de QA garante não só a qualidade final do produto, mas todo o processo de produção do software. Isso inclui: os requisitos iniciais, a implantação/implementação do que foi estipulado pelo cliente e pelos projetistas, se as boas práticas foram seguidas ou não durante o processo, até os testes finais do software pronto antes de entregar ao cliente.

## Relações

QC é mais particular e restrito — sua responsabilidade se limita à qualidade do produto final. QA é mais universal em matéria de qualidade: gerencia não só a qualidade do software em si, mas tudo o que é relativo a ele — a metodologia de trabalho usada, o processo de produção como um todo.

Na prática, QC está contido dentro de QA: toda atividade de QC (testar o produto pronto) acontece dentro do processo maior que QA supervisiona. Por isso, uma falha encontrada nos testes finais (QC) ainda é, em última instância, uma responsabilidade que recai sobre o processo de QA como um todo — os dois continuam coexistindo no mesmo cenário.

Em empresas pequenas, onde uma única pessoa acompanha os requisitos, o processo e também roda os testes finais, faz mais sentido chamá-la de profissional de QA — porque, cobrindo o processo inteiro, ela já engloba naturalmente o papel de QC, mesmo sem o cargo existir separadamente ali.

## Exemplos

- Revisar se um code review foi feito antes do merge → QA (auditoria de processo, não é teste).
- Verificar se os requisitos foram documentados corretamente antes de começar a codificar → QA.
- Rodar o sistema pronto e comparar com o que foi combinado no requisito para achar uma divergência → QC (mas a responsabilidade maior pelo motivo da divergência não ter sido pega antes continua sendo do processo de QA).

---

## Nova entrada — 17/09/2026 | Fonte: Faculdade ADS

## Qualidade de Processos x Qualidade de Produtos

A qualidade de software pode ser olhada por dois ângulos complementares:

- **Qualidade de Processos:** organiza e padroniza os métodos de trabalho da equipe, buscando uma cultura de não tolerância a erros para prevenir falhas, otimizando prazos, estimativas de custo e alocação de recursos. É avaliada por modelos de maturidade.
- **Qualidade de Produtos:** avalia o artefato tecnológico gerado durante o ciclo de desenvolvimento, aplicando baterias de testes para garantir que o sistema atenda aos requisitos do cliente antes da entrega.

Essa distinção se conecta diretamente com o que já foi registrado aqui sobre QA e QC: Qualidade de Processos é, essencialmente, o que o profissional de QA supervisiona; Qualidade de Produtos é o que o profissional de QC avalia no produto pronto.

## Modelos de Maturidade de Processos

Para avaliar formalmente a Qualidade de Processos, existem modelos de maturidade reconhecidos:

- **CMMI (Capability Maturity Model Integration):** modelo internacional com 5 níveis — Inicial (caótico), Gerenciado, Definido, Gerenciado Quantitativamente e Otimizado.
- **MPS.BR (Melhoria do Processo de Software Brasileiro):** modelo nacional com 7 níveis, em ordem crescente — G (Parcialmente Gerenciado, nível de entrada), F (Gerenciado), E (Parcialmente Definido), D (Largamente Definido), C (Definido), B (Gerenciado Quantitativamente) e A (Em Otimização).

---

## Nova entrada — 18/09/2026 | Fonte: Faculdade ADS

## Gerenciamento da Qualidade: três níveis hierárquicos

O gerenciamento da qualidade se estrutura em três pilares hierárquicos, que aprofundam a distinção entre QA e QC já registrada aqui:

- **Garantia da Qualidade (nível organizacional):** vem da cúpula da empresa. Define a cultura, os procedimentos, padrões e ferramentas organizacionais. Se a garantia não é estabelecida no topo, gera-se um efeito cascata que desestrutura todo o trabalho de desenvolvimento.
- **Planejamento da Qualidade (nível do projeto):** adapta o plano geral da empresa para as necessidades e metas específicas de um determinado software ou momento.
- **Controle da Qualidade (nível operacional):** executa a verificação no dia a dia para garantir que os processos e o plano do projeto estejam sendo seguidos na prática.

## Independência das equipes (princípio de Sommerville)

A equipe de desenvolvimento não deve ser responsável pelo próprio controle de qualidade. O desenvolvedor possui um "ponto cego" — não necessariamente por má-fé, mas por viés de confirmação e acidentes não percebidos. Ter uma equipe separada garante imparcialidade na avaliação técnica.

---

## Nova entrada — 19/09/2026 | Fonte: Faculdade ADS (Engenharia de Software)

## SQA (proativo) x QC (reativo)

Aprofundando a distinção entre Qualidade de Processo e Qualidade de Produto já registrada aqui:

- **Qualidade do Processo (Garantia da Qualidade / SQA):** natureza proativa. Foca em como o software é desenvolvido — padrões, procedimentos, modelos de maturidade (CMMI, MPS.BR) e prevenção de falhas antes que afetem o produto.
- **Qualidade do Produto (Controle da Qualidade / QC):** natureza reativa. Foca no resultado final e em artefatos intermediários, por meio de testes funcionais, medições e verificações, visando garantir a satisfação do cliente.

**Efeito da falta de processo:** focar apenas na qualidade do produto (testes no final) gera alto volume de retrabalho e não impede a geração contínua de erros já na fase de escrita de código.

**Nota sobre a nomenclatura — por que "SQA" tem o "S" e "QC" não:** QA e QC, na forma curta, são termos que vêm da gestão da qualidade em geral (indústria, manufatura, normas como a família ISO 9000), aplicáveis a qualquer tipo de produto. SQA (*Software Quality Assurance*) é usado quando o texto quer deixar explícito que está tratando da aplicação desses princípios especificamente ao contexto de software — é comum em obras acadêmicas de Engenharia de Software, como Pressman. A ausência do "S" em QC não reflete uma distinção técnica de peso: é uma assimetria de convenção da literatura, não uma regra lógica.