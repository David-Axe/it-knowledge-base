# Diagramas UML

**Fonte:** Faculdade ADS — Engenharia de Software (livro-texto: Sommerville, Larman, Fowler)
**Data:** 03/09/2026

## O que é e onde se encaixa

A fase de projeto (design) é a etapa intermediária entre o levantamento de requisitos e a implementação (codificação) do sistema. É a ponte entre o que o cliente quer e o que será efetivamente construído — como o projetista que traduz o pedido do cliente para que o marceneiro consiga executar.

## Por que existe

Existe por dois motivos interligados: primeiro, para garantir que o software seja feito exatamente da forma que o cliente deseja, traduzindo requisitos (muitas vezes vagos ou ambíguos) em algo concreto e executável sem perda de fidelidade. Segundo, para evitar qualquer coisa que atrapalhe esse objetivo — retrabalho, mal-entendidos, decisões tomadas sem planejamento — o que sairia caro se só fosse percebido depois de pronto.

## Divisão: alto nível x baixo nível

O projeto se divide em duas partes. O projeto de alto nível é a visão geral — no caso da marcenaria, seria o projeto renderizado apresentado ao cliente, focado na estética ("ficou bonito assim"). O projeto de baixo nível já é o detalhado, feito para quem vai executar: medidas exatas, materiais, cores, tipo de puxador, dobradiças — o equivalente ao projeto hidráulico ou elétrico de uma casa, feito para quem trabalha especificamente com aquilo. O cliente normalmente só tem contato com o alto nível; o baixo nível é para quem constrói.

Dentro disso, Sommerville descreve quatro atividades: projeto de arquitetura (a planta baixa — estrutura geral e como as partes se relacionam), projeto de interface (o "padrão de tomada" — como os componentes se comunicam sem precisar saber como o outro funciona por dentro), projeto de componente (o funcionamento interno de uma peça isolada, como a dobradiça de um armário) e projeto de banco de dados (como os dados ficam organizados e armazenados).

## UML — o que é e por que surgiu

UML (*Unified Modeling Language* — Linguagem de Modelagem Unificada) é uma linguagem visual padronizada para representar a estrutura e o comportamento de um sistema — uma espécie de protocolo de comunicação entre humanos, no mesmo espírito do TCP/IP entre máquinas: garante que um diagrama feito por uma pessoa seja lido sem ambiguidade por outra.

Ela surgiu nos anos 1990 como unificação de vários métodos de modelagem concorrentes e incompatíveis que existiam desde as décadas de 70-80 — cada equipe com sua própria notação, sem conseguir se comunicar com times que usavam outro método. A UML resolveu esse "vale-tudo".

## As três formas de uso (Fowler)

- **Rascunho (sketch):** diagramas informais, feitos rapidamente para explorar uma ideia — compreensíveis principalmente para quem os fez.
- **Planta de software (blueprint):** diagramas mais formais, usados em engenharia reversa (ler um código existente e gerar o diagrama, para entender um sistema legado) ou engenharia avante (o diagrama guia a criação do código). É uma ferramenta que potencializa a capacidade de quem projeta e de quem precisa entender o sistema — não é a solução completa por si só.
- **Linguagem de programação:** o caso extremo, em que a especificação em UML já é completa o bastante para que o código executável seja gerado automaticamente, bastando um "tradutor". É como a cadeia entre o programador, a linguagem de alto nível (mais próxima do pensamento humano) e o binário (linguagem de baixo nível, mais próxima da máquina) — nessa forma, a UML ocuparia o lugar da linguagem de alto nível, e o gerador de código seria o tradutor/compilador.

## As três perspectivas (Larman)

O mesmo diagrama pode ser lido de formas diferentes dependendo do papel de quem olha — como "óculos" que não se trocam conscientemente, mas vêm da função que a pessoa ocupa (como o olhar clínico de um médico ou o senso jurídico de um advogado):

- **Perspectiva conceitual:** o diagrama representa algo do mundo real ou do domínio de negócio (cliente, pedido, produto) — típica de quem está levantando requisitos.
- **Perspectiva de especificação:** representa abstrações de software (componentes, interfaces), sem se comprometer com uma linguagem específica.
- **Perspectiva de implementação:** representa o código já numa tecnologia concreta (Java, Python etc.) — o olhar de quem está desenvolvendo.
