# Teorema CAP

Data: 15/10/2026 | Fonte: Faculdade ADS

Em qualquer sistema de banco de dados distribuído (com dados espalhados por vários nós em rede, como nos [[banco-de-dados/arquitetura-de-sgbd|bancos distribuídos]]), é impossível garantir simultaneamente três propriedades:

1. **C (Consistência, *Consistency*):** todos os nós enxergam exatamente os mesmos dados ao mesmo tempo.
2. **A (Disponibilidade, *Availability*):** toda requisição recebe uma resposta, sem travamentos.
3. **P (Tolerância à partição, *Partition Tolerance*):** o sistema continua operando mesmo quando há falha de comunicação entre os nós da rede. Uma partição é a rede dividida em grupos de nós que não conseguem se comunicar.

## Aplicação no NoSQL

Falhas de rede acontecem em sistemas distribuídos, então a tolerância à partição não é opcional. Na prática, a escolha fica entre consistência e disponibilidade quando a rede falha. Muitos bancos NoSQL priorizam Disponibilidade + Tolerância à partição (AP), adotando a consistência eventual do [[banco-de-dados/nosql|modelo BASE]]. Outros priorizam Consistência + Tolerância à partição (CP).

Esse compromisso ajuda a entender a dificuldade de manter réplicas sincronizadas em bancos distribuídos, citada em [[banco-de-dados/arquitetura-de-sgbd|arquitetura de SGBD]].