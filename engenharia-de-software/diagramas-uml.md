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

- ---

## Nova entrada — 04/09/2026 (continuação)

**Os cinco diagramas mais usados**

Além da introdução ao UML, existem cinco diagramas mais usados para representar um sistema: atividades, casos de uso, sequência, classe e estado. O diagrama de atividades mostra o fluxo de um processo, uma sequência de tarefas acontecendo uma depois da outra. O diagrama de casos de uso mostra a interação entre o sistema e o usuário, de forma mais abstrata, sem entrar em como isso acontece por dentro. O diagrama de classe mostra a estrutura estática: o que existe no sistema e como as partes se relacionam. O diagrama de estado mostra como o sistema (ou algo dentro dele, como um pedido) reage a eventos, mudando de uma condição para outra.

**Diagrama de atividades x diagrama de estado**

O diagrama de atividades descreve o processo, a tarefa em execução — uma sequência de ações acontecendo uma depois da outra. No caso de um pedido de móvel numa marcenaria, seria algo como: conversar com o cliente, elaborar o projeto, fechar o pedido, cobrar a entrada, calcular chapas e peças, cortar na CNC, montar o móvel, transportar, instalar, cobrar o valor final e fazer o pós-venda. É o "fazer" — cada etapa leva à próxima.

O diagrama de estado é diferente: ele não descreve a tarefa em execução, mas a situação em que algo se encontra em um dado momento, e o que faz essa situação mudar. Essa mudança é disparada por um evento, e um mesmo estado pode ter mais de um caminho possível a partir dele (uma bifurcação) — o que não acontece numa lista de atividades puramente linear.

Um exemplo de estado, ainda na marcenaria: "móvel instalado, aguardando aprovação do cliente". Se o cliente aprova (evento), o pedido passa para o estado "aguardando cobrança". Do outro lado dessa mesma bifurcação, se o cliente não aprova, o pedido iria para outro estado (a definir — provavelmente algo como "ajuste solicitado" ou "revisão do móvel"), em vez de seguir direto para a cobrança.

**Diagrama de sequência x diagrama de comunicação**

Esses dois diagramas mostram a mesma informação — quais mensagens são trocadas entre os objetos de um sistema — mas de formas diferentes. O diagrama de sequência usa a posição vertical (de cima para baixo) para indicar a ordem das mensagens. O diagrama de comunicação usa números escritos ao lado das setas para indicar essa ordem, e organiza os objetos livremente, sem depender de uma linha do tempo vertical.

O diagrama de sequência é mais fácil de ler, porque a ordem já está visualmente clara. Já o diagrama de comunicação é mais fácil de desenhar rápido, porque não precisa "esticar" o diagrama para a direita a cada novo objeto — o que faz sentido com a ideia de "UML como rascunho" vista anteriormente: comunicação tende a ser mais usado como rascunho rápido, e sequência como documentação mais detalhada.
