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
