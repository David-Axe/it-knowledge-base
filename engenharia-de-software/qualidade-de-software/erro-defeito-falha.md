# Erro, Defeito e Falha

Data: 17/09/2026 | Fonte: Faculdade ADS

Segundo Koscianski e Soares (2007), a manifestação de problemas no software se divide em três estágios distintos, numa cadeia de causa e efeito:

- **Erro:** equívoco, ação incorreta ou engano humano cometido durante a análise, o projeto ou a codificação do software.
- **Defeito:** imperfeição técnica ou anomalia estática presente no código-fonte ou na documentação, decorrente do erro humano.
- **Falha:** evento em tempo de execução em que o sistema manifesta um comportamento incorreto, um resultado inválido ou uma interrupção do funcionamento perante o usuário final.

Essa cadeia ajuda a entender por que um mesmo problema pode ser pego em momentos diferentes: um Erro pode ser identificado ainda na fase de análise estática, antes de virar Defeito no código; um Defeito pode ser pego em [[verificacao-validacao-e-testes|verificação]], antes de chegar a se manifestar como Falha durante a execução real do sistema, que é o que os [[teste-de-software|testes]] tentam expor.