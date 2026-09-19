# Erro, Defeito e Falha

Data: 17/09/2026 | Fonte: Faculdade ADS

Segundo Koscianski e Soares (2007), a manifestação de problemas no software se divide em três estágios distintos, numa cadeia de causa e efeito:

- **Erro:** equívoco, ação incorreta ou engano humano cometido durante a análise, o projeto ou a codificação do software.
- **Defeito:** imperfeição técnica ou anomalia estática presente no código-fonte ou na documentação, decorrente do erro humano.
- **Falha:** evento em tempo de execução em que o sistema manifesta um comportamento incorreto, um resultado inválido ou uma interrupção do funcionamento perante o usuário final.

Essa cadeia ajuda a entender por que um mesmo problema pode ser pego em momentos diferentes: um Erro pode ser identificado ainda na fase de análise estática, antes de virar Defeito no código; um Defeito pode ser pego em [[verificacao-validacao-e-testes|verificação]], antes de chegar a se manifestar como Falha durante a execução real do sistema, que é o que os [[teste-de-software|testes]] tentam expor.

---

## Nova entrada — 19/09/2026 | Fonte: Faculdade ADS (Engenharia de Software)

## Nota Teórica: duas tradições diferentes para Erro, Defeito e Falha

Na Engenharia de Software, os termos Erro, Defeito e Falha possuem duas abordagens teóricas consagradas, a depender do foco da análise:

**Abordagem 1 — Abordagem 1 — Cadeia Técnica de Causa e Efeito (norma IEEE 610.12 / ISTQB), já registrada acima segundo Koscianski e Soares (2007), tradição também seguida por autores como Sommerville: focada no comportamento técnico do código e na execução do sistema — Erro é o engano humano, Defeito é a imperfeição estática no código decorrente desse erro, e Falha é o comportamento incorreto manifestado em tempo de execução.

**Abordagem 2 — Linha do Tempo e Gestão do Processo (Pressman & Maxim, 2016)**: focada na Garantia da Qualidade (SQA) e no momento do ciclo de vida em que o problema é descoberto — Erro é o problema de qualidade identificado pela própria equipe **antes** do envio do software ao cliente (durante revisões, inspeções ou testes internos); Defeito é o problema identificado pelo cliente ou usuário final **depois** da entrega, em ambiente de produção.

As duas abordagens não são contraditórias — são enquadramentos diferentes, cada um servindo a um propósito de análise diferente: a primeira ajuda a entender tecnicamente onde e como um problema se origina; a segunda ajuda a gestão a medir o impacto econômico e de imagem de um problema, dependendo de quando ele foi descoberto.