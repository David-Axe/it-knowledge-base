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

----

## Nova entrada — **Fonte:** Faculdade ADS 04/09/2026 (continuação)

**Os cinco diagramas mais usados**

Além da introdução ao UML, existem cinco diagramas mais usados para representar um sistema: atividades, casos de uso, sequência, classe e estado. O diagrama de atividades mostra o fluxo de um processo, uma sequência de tarefas acontecendo uma depois da outra. O diagrama de casos de uso mostra a interação entre o sistema e o usuário, de forma mais abstrata, sem entrar em como isso acontece por dentro. O diagrama de classe mostra a estrutura estática: o que existe no sistema e como as partes se relacionam. O diagrama de estado mostra como o sistema (ou algo dentro dele, como um pedido) reage a eventos, mudando de uma condição para outra.

**Diagrama de atividades x diagrama de estado**

O diagrama de atividades descreve o processo, a tarefa em execução — uma sequência de ações acontecendo uma depois da outra. No caso de um pedido de móvel numa marcenaria, seria algo como: conversar com o cliente, elaborar o projeto, fechar o pedido, cobrar a entrada, calcular chapas e peças, cortar na CNC, montar o móvel, transportar, instalar, cobrar o valor final e fazer o pós-venda. É o "fazer" — cada etapa leva à próxima.

O diagrama de estado é diferente: ele não descreve a tarefa em execução, mas a situação em que algo se encontra em um dado momento, e o que faz essa situação mudar. Essa mudança é disparada por um evento, e um mesmo estado pode ter mais de um caminho possível a partir dele (uma bifurcação) — o que não acontece numa lista de atividades puramente linear.

Um exemplo de estado, ainda na marcenaria: "móvel instalado, aguardando aprovação do cliente". Se o cliente aprova (evento), o pedido passa para o estado "aguardando cobrança". Do outro lado dessa mesma bifurcação, se o cliente não aprova, o pedido iria para outro estado (a definir — provavelmente algo como "ajuste solicitado" ou "revisão do móvel"), em vez de seguir direto para a cobrança.

**Diagrama de sequência x diagrama de comunicação**

Esses dois diagramas mostram a mesma informação — quais mensagens são trocadas entre os objetos de um sistema — mas de formas diferentes. O diagrama de sequência usa a posição vertical (de cima para baixo) para indicar a ordem das mensagens. O diagrama de comunicação usa números escritos ao lado das setas para indicar essa ordem, e organiza os objetos livremente, sem depender de uma linha do tempo vertical.

O diagrama de sequência é mais fácil de ler, porque a ordem já está visualmente clara. Já o diagrama de comunicação é mais fácil de desenhar rápido, porque não precisa "esticar" o diagrama para a direita a cada novo objeto — o que faz sentido com a ideia de "UML como rascunho" vista anteriormente: comunicação tende a ser mais usado como rascunho rápido, e sequência como documentação mais detalhada.

---

## Nova entrada — **Fonte:** Faculdade ADS 04/09/2026

## Diagrama de Casos de Uso

O diagrama de casos de uso mostra quem interage com o sistema e o que essas pessoas conseguem fazer com ele, sem entrar em como o sistema faz isso por dentro. Ele existe para colocar o foco no usuário: em vez de simplesmente listar características técnicas do sistema, ele força a pergunta "quem usa o sistema, e o que essa pessoa quer alcançar?".

**Elementos:** um ator é algo com comportamento — uma pessoa (identificada pelo papel, não pelo nome), um sistema externo ou uma organização. Um caso de uso é a própria funcionalidade, sempre nomeada com um verbo, porque o verbo indica ação — e ação é justamente o que esse diagrama quer capturar (o que o sistema faz), diferente de um substantivo, que descreveria uma coisa ou estrutura (papel de outro diagrama, como o de classe).

**Relacionamentos:** a associação é a ligação simples entre um ator e um caso de uso. A generalização é quando um caso de uso "filho" herda o comportamento de um "pai". E existem duas formas de dependência: o include, quando um caso de uso precisa obrigatoriamente do outro para acontecer, e o extend, quando é uma variação opcional que só ocorre em certas condições.

**Exemplo (marcenaria):** os atores seriam o cliente e o projetista. Os casos de uso: Projetar, Aprovar, Confeccionar e Acrescentar. Confeccionar inclui obrigatoriamente Aprovar (não dá pra confeccionar sem o projeto ter sido aprovado antes). Acrescentar estende Aprovar (é uma variação opcional, que só acontece às vezes, durante o processo de aprovação).

**Cenário x caso de uso — uma dúvida importante que resolvi durante o estudo:** no início, pensei que um cenário viria depois do caso de uso — por exemplo, que "aprovado sem mudança", "aprovado com acréscimo" e "reprovado por orçamento" seriam consequências posteriores do caso de uso Aprovar. Mas não é assim: o cenário é um caminho através do próprio caso de uso, não algo que vem depois dele. É como perguntar se o gol aconteceu antes ou depois da jogada — não faz sentido, porque o gol é uma das formas possíveis de a própria jogada terminar, não uma coisa que vem depois. Da mesma forma, "aprovado sem mudança" e as outras variações não vêm depois do caso de uso Aprovar — elas são o próprio Aprovar acontecendo de diferentes formas possíveis.

---

## Nova entrada — **Fonte:** Faculdade ADS 05/09/2026

## Especificação de Casos de Uso

A especificação de casos de uso é um texto detalhado que acompanha o diagrama de casos de uso, descrevendo com precisão o que acontece em cada caso — os caminhos possíveis, as condições e os resultados — sem entrar em como o sistema implementa isso. Ela existe porque o diagrama sozinho é enxuto demais: mostra quais casos de uso existem e quem os aciona, mas não diz, por exemplo, o que acontece se um campo obrigatório for deixado em branco. Mesmo assim, a especificação continua em alto nível, porque não é usada apenas pelo time de desenvolvimento — clientes e gerentes também precisam entendê-la.

Modelo RUP (Rational Unified Process): um formato comum de especificação textual possui oito campos: nome do caso de uso, breve descrição, fluxo básico (o caminho padrão de sucesso), fluxos alternativos (os desvios, que podem conter subfluxos), requisitos especiais (exigências que não aparecem na narrativa, como tempo de resposta), condições prévias (o que precisa ser verdade antes de o caso de uso executar), condições posteriores (o que precisa ser verdade depois que ele termina) e pontos de extensão (onde esse caso de uso pode se conectar a outro através de extend).

Diagramas comportamentais x estruturais: a UML separa os diagramas em comportamentais (descrevem o que o sistema faz — caso de uso, atividades, sequência, estado) e estruturais (descrevem o que existe — como o diagrama de classes). A especificação de casos de uso normalmente é produzida antes do diagrama de atividades, porque fornece uma visão mais ampla e geral do comportamento do sistema, que depois pode ser detalhada passo a passo pelo diagrama de atividades.

Pré-condição e pós-condição — uma dúvida que resolvi durante o estudo: a pré-condição é aquilo que já precisa ser verdadeiro antes da execução do caso de uso. A pós-condição não é apenas uma frase resumindo o resultado final, mas um conjunto de fatos concretos e verificáveis que passam a ser verdade ao término de um determinado cenário. Como um mesmo caso de uso pode possuir mais de um cenário (sucesso, reprovação, cancelamento etc.), cada cenário possui suas próprias pós-condições.

Aplicando isso ao exemplo da marcenaria, no caso de uso "Aprovar", a pré-condição é que o projeto tenha sido concluído e enviado ao cliente. No cenário de sucesso, as pós-condições são: o projeto está marcado como aprovado, o cliente recebeu a confirmação e o caso de uso "Confeccionar" está liberado para iniciar. No cenário de reprovação, as pós-condições são: o projeto está marcado como reprovado, as observações do cliente foram registradas e um novo ciclo de "Projetar" (ajuste) está liberado para começar.

## Ajustes e refinamentos a conceitos anteriores

Os cinco diagramas não são obrigatórios. Na entrada anterior, apresentei cinco diagramas bastante utilizados (atividades, casos de uso, sequência, classes e estado). Durante a continuação do estudo, ficou mais claro que não existe uma sequência fixa de utilização nem a necessidade de empregar todos eles em um projeto. A escolha dos diagramas depende da necessidade de cada sistema. Um projeto simples pode exigir apenas alguns deles, enquanto projetos mais complexos podem justificar o uso de vários.

Também ficou mais consolidado para mim como esses diagramas se distribuem ao longo do processo de desenvolvimento — algo que já estava implícito na estrutura da minha primeira entrada sobre esse tema (que começava pela fase de projeto e só depois introduzia o UML), mas que na hora não tinha profundidade suficiente para realmente fazer sentido. Em geral, os diagramas pertencem à fase de projeto (design), que ocorre após o levantamento de requisitos. Entretanto, o caso de uso possui uma característica especial: ele já começa a aparecer ainda na etapa de requisitos, funcionando como uma ponte entre o entendimento do negócio e o projeto do sistema.

UML como "biblioteca com protocolo interno", não como protocolo puro. Em uma entrada anterior, comparei a UML como um todo a um protocolo de comunicação, semelhante ao TCP/IP. Durante a revisão do tema, percebi uma analogia mais precisa: a UML se parece mais com uma biblioteca de ferramentas de modelagem.

Cada diagrama é uma ferramenta disponível para representar determinado aspecto de um sistema, mas a utilização de um diagrama não obriga a utilização dos demais. Por outro lado, cada ferramenta dessa biblioteca possui regras rígidas de representação. Nesse sentido, a analogia com um protocolo continua válida: os símbolos e significados de cada diagrama não podem ser reinterpretados livremente sem comprometer a comunicação entre as pessoas que os utilizam.

Em resumo: a UML funciona como uma biblioteca de ferramentas, mas cada ferramenta dentro dessa biblioteca segue um protocolo de representação bem definido.

---

## Nova entrada — **Fonte:** Faculdade ADS 07/09/2026

## Ajustes e refinamentos a conceitos anteriores

Diagrama e especificação de casos de uso não são coisas separadas — são duas representações complementares do mesmo caso de uso. Isso já estava implícito na entrada anterior (que definia a especificação como "um texto detalhado que acompanha o diagrama"), mas retomando o tema ficou muito mais clara a relação entre os dois: o diagrama é a representação gráfica, resumida — mostra quem faz o quê. A especificação é a representação textual, detalhada — descreve como aquele mesmo caso de uso se desenrola, passo a passo, com pré-condições, pós-condições e fluxos alternativos.

Os dois não substituem um ao outro, e não fazem sentido plenamente separados: a especificação sem o diagrama perde a visão geral rápida que o diagrama oferece; o diagrama sem a especificação deixa lacunas — não diz o que acontece quando algo foge do caminho padrão. Por isso os dois subsistem juntos: o diagrama dá o mapa, a especificação dá o passo a passo de cada trecho desse mapa.

## Diagrama de Atividades

O diagrama de atividades é um dos diagramas comportamentais mais completos da UML[cite: 1]. Enquanto o diagrama de casos de uso fornece uma visão macro — mostrando quem interage com o sistema e quais funcionalidades principais ele aciona —, o diagrama de atividades desce para o "como funcional", detalhando passo a passo a execução interna de uma rotina[cite: 1]. Ele funciona graficamente de forma semelhante aos fluxogramas tradicionais da administração de empresas[cite: 1], permitindo documentar aspectos funcionais, esclarecer requisitos e mapear fluxos complexos.

**Quando utilizar:** Assim como os demais diagramas da UML, ele não é de uso obrigatório em todos os projetos. Sua aplicação faz sentido em contextos específicos que exigem maior detalhamento, como sistemas críticos onde uma falha gera grande impacto, cenários em que o cliente precisa visualizar com clareza o fluxo operacional (ajudando a alinhar o software à rotina real do negócio)[cite: 1], ou projetos que dispõem de tempo para uma documentação aprofundada.

**Elementos fundamentais:**
* **Estados iniciais e finais:** Marcam o início e o encerramento do fluxo[cite: 1].
* **Atividades:** Representam as ações executadas pelo sistema[cite: 1].
* **Decisões:** Pontos em que o fluxo pode seguir caminhos distintos com base em condições[cite: 1] (por exemplo, verificar se um produto já está cadastrado ou se um pedido está pago).
* **Bifurcação e união:** Permiten dividir fluxos para que ocorram de forma concomitante e, posteriormente, reuni-los[cite: 1].
* **Raias (Swimlanes):** Organizam o diagrama delimitando responsabilidades entre atores, objetos ou componentes do sistema (como Cliente, Vendas e Estoque)[cite: 1].

**Analogia estrutural — Raias e o modelo TCP/IP:** 
Pensando em arquitetura, as raias funcionam de forma semelhante às camadas do modelo de redes TCP/IP: cada parte do sistema (ou setor da empresa) tem sua responsabilidade bem delimitada e executa sua função dentro de uma divisão clara de papéis. No entanto, diferentemente de um protocolo de rede estrito — onde as regras devem ser seguidas rigidamente "sim ou sim" —, os processos de negócio reais lidam com o fator humano e caminhos alternativos (como um cliente que desiste da compra no meio do caminho), exigindo que o diagrama preveja essas variações para evitar falhas operacionais e gargalos de comunicação entre diferentes setores.