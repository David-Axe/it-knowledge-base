# Engenharia de Software Baseada em Componentes (CBSE)

Data: 26/09/2026 | Fonte: Faculdade ADS

## Contexto e Motivação

A CBSE (Component-Based Software Engineering) surgiu no final dos anos 1990 para superar as limitações do reúso na Orientação a Objetos (OO) tradicional.

- **Limitação da OO:** as classes eram detalhadas e específicas demais para cenários genéricos, exigindo acoplamento forte e conhecimento do código-fonte para reaproveitamento.
- **Mudança de paradigma:** a CBSE altera o foco do desenvolvimento da programação do zero para a composição e integração de sistemas ("compre/reuse, não construa").

## O que é um Componente de Software?

É uma unidade independente, autônoma e executável de código que fornece serviços por meio de interfaces bem definidas.

- **Formatos comuns:** executáveis (.exe, .jar), bibliotecas (.dll), componentes de interface (ex.: componentes React) e pacotes web.
- **Comunicação por interfaces:** a conexão entre componentes ocorre exclusivamente via contratos de interface, frequentemente representados pelo modelo *lollipop* (pirulito) — uma notação gráfica em que a interface fornecida por um componente (o que ele oferece) é desenhada como um círculo preso por uma linha, e a interface requerida por outro (o que ele precisa) é desenhada como um semicírculo aberto que "encaixa" no círculo do primeiro, mostrando visualmente a compatibilidade entre os dois sem expor a implementação interna de nenhum deles.

## Comparativo: Objeto x Componente

| Característica | Objeto | Componente |
| :--- | :--- | :--- |
| **Escopo** | Unidade de instanciação e regra de negócio. | Unidade de implantação e composição. |
| **Estado** | Possui estado (que pode ser persistente em banco de dados). | Não possui estado persistente (unidade executável/serviço). |
| **Encapsulamento** | Encapsula estado e comportamento. | Encapsula implementação completa atrás de interfaces de contrato. |

## O Ciclo de Desenvolvimento em CBSE

A CBSE divide o processo de engenharia em dois fluxos distintos:

1. **Desenvolvimento PARA reúso:** foco em criar componentes genéricos, flexíveis e altamente testados para integrar um repositório. Exige de 3 a 5 vezes mais esforço/custo inicial, devido à necessidade de generalização e documentação rigorosa.
2. **Desenvolvimento COM reúso:** foco em selecionar, adaptar e montar componentes pré-existentes do repositório para construir uma aplicação específica. Reduz drasticamente o *time-to-market* (tempo até chegar ao mercado), o tempo de codificação e os custos do projeto final.

## Análise de Custos, Benefícios e Riscos

**Benefícios:** redução do tempo de desenvolvimento (uso de blocos já prontos e testados); manutenibilidade (facilidade para substituir ou atualizar módulos obsoletos sem impactar o sistema inteiro); padronização (arquiteturas baseadas em padrões comerciais, como COTS — *Commercial Off-The-Shelf*, produtos prontos disponíveis no mercado).

**Riscos e desvantagens:** alto custo inicial (investimento de tempo/dinheiro na criação do repositório de componentes); conflito usabilidade x reusabilidade (quanto mais genérico e configurável for o componente, mais complexa se torna sua utilização); dependência e evolução (risco de falhas em cascata caso uma atualização no componente quebre a compatibilidade com a aplicação).

## Analogias para fixação

- **O castelo de Lego:** o desenvolvimento OO tradicional equivale a montar um castelo peça por peça. A CBSE equivale a utilizar módulos pré-montados (muralhas, torres, portões) e apenas encaixá-los para formar diferentes configurações de castelo, de forma rápida.
- **O home theater:** em vez de comprar um aparelho único e fechado (monolítico), utilizam-se componentes independentes (TV, caixas de som, receiver) conectados por cabos e interfaces padrão (HDMI). Qualquer peça pode ser trocada individualmente sem descartar o sistema completo.

---

## Nova entrada — 26/09/2026 | Fonte: Faculdade ADS — Capítulo 2: Desenvolvimento Orientado a Reúso de Software (Marcelo da Silva dos Santos)

## As 5 Características Fundamentais de um Componente (Sommerville, 2019)

1. **Padronizável:** deve seguir um modelo de componentes padrão que defina suas interfaces, metadados, documentação, composição e implantação.
2. **Independente:** deve ser autônomo, não dependendo de outros componentes específicos para funcionar. Caso necessite de serviços externos, estes devem estar explicitamente declarados em sua interface exigida (*required*).
3. **Passível de composição:** suas interfaces públicas devem permitir a interação com outros elementos do sistema e o acesso controlado a seus métodos e atributos — trata da especificação dos "plugues e tomadas" de conexão.
4. **Implantável:** é autossuficiente para operar sobre a plataforma que implementa o modelo de componentes. É disponibilizado em formato binário executável (como .dll, .jar, .exe), dispensando o acesso ao código-fonte original ou recompilação prévia.
5. **Documentado:** deve possuir documentação integral sobre a sintaxe e a semântica de suas interfaces, para que os desenvolvedores saibam se ele atende às necessidades do sistema.

## O que é um Modelo de Componentes?

Um Modelo de Componentes define o conjunto de padrões e convenções necessários para a construção, documentação, composição e implantação de um componente — as regras de como as peças devem ser desenvolvidas para se encaixarem perfeitamente numa aplicação.

**Exemplos de modelos e tecnologias:**

- **CORBA (Common Object Request Broker Architecture):** modelo mantido pela OMG, com linguagem de definição de interfaces (IDL).
- **COM (Component Object Model):** modelo da Microsoft para componentes binários distribuídos.
- **EJB (Enterprise JavaBeans):** modelo da plataforma Java Enterprise Edition, para componentes transacionais, distribuídos e seguros, executados em contêineres.
- **Componentes Web (Web Components):** padrão da W3C para encapsulamento e reutilização de elementos HTML/JavaScript em navegadores.
- Outros ecossistemas: plataforma Delphi (biblioteca vasta de componentes nativos) e frameworks web (como Zend Framework).

**Estrutura de um Modelo de Componentes** — três pilares principais:

- **Interfaces:** define como os contratos são especificados (ex.: WSDL/XML para Web Services, Java para EJB, CIL para .NET).
- **Informações de Uso:** estabelece convenções de nomes (identificadores globais únicos por GUID ou por domínio invertido), regras de acesso a metadados (ex.: reflexão) e mecanismos de customização.
- **Implantação e Uso:** define os formatos de empacotamento executável, suporte à evolução/atualização de versão, documentação acoplada e os serviços requeridos do middleware.

## Interfaces do Componente: Provida x Exigida

Complementando o modelo lollipop já registrado acima: a comunicação do componente com o mundo exterior é feita estritamente por meio de interfaces, que funcionam como contratos formais.

- **Interface Fornecida (Provided):** os serviços e métodos que o componente oferece para outros sistemas consumirem. Representação UML: círculo/pirulito.
- **Interface Exigida (Required):** os serviços e recursos externos que o componente necessita para executar sua tarefa. Representação UML: semicírculo/soquete — que "encaixa" no pirulito do componente que fornece aquele serviço.

**Risco prático:** se a assinatura de um método na interface fornecida for alterada sem aviso prévio, a garantia do contrato é quebrada, gerando erros fatais ("Method Not Found") em todos os sistemas consumidores daquele componente.

## Serviços do Modelo de Componentes e Infraestrutura

A implementação de um modelo de componentes depende de uma camada de **middleware** (software que atua como ponte de comunicação entre componentes e sistemas). Os serviços da infraestrutura se dividem em duas categorias:

- **Serviços de Plataforma:** essenciais para permitir a comunicação e a interoperabilidade dos componentes em um ambiente distribuído — definição de interfaces, gerenciamento de exceções, endereçamento e transporte de mensagens.
- **Serviços de Suporte:** serviços comuns compartilhados por todos os componentes, reduzindo o custo de desenvolvimento e evitando duplicação — autenticação, gerenciamento de dados/transações, filas de mensagens e gestão de APIs.

**Contêineres de middleware:** o componente é implantado dentro de um contêiner, que o encapsula, garante isolamento e fornece acesso automático aos serviços de suporte. Se um componente falhar, a falha fica contida em seu contêiner, impedindo a queda de toda a aplicação e facilitando sua substituição. Para aplicações mais simples, uma abordagem alternativa é a arquitetura de Serviços Web, importando apenas bibliotecas específicas sob demanda, evitando a sobrecarga de memória e processamento de um contêiner tradicional completo.

---

## Nova entrada — 26/09/2026 | Fonte: Curiosidade durante estudo na Faculdade ADS — exploração superficial com IA

**Nível de domínio: Conceitual/Panorâmico.**

## Como funciona o "montar o LEGO" na prática

Complementando os dois fluxos de desenvolvimento já registrados acima:

- **Desenvolvimento PARA reúso, na prática:** o desenvolvedor projeta e programa o componente do zero dentro do editor (ex.: VS Code), define suas interfaces e o empacota para ser publicado em repositórios (como npm, NuGet ou Maven).
- **Desenvolvimento COM reúso, na prática:** o desenvolvedor não programa as regras de negócio internas novamente. Ele usa gerenciadores de pacotes no terminal para baixar o componente e escreve o **Código de Cola** (*Glue Code*) — o trecho de código escrito exclusivamente para fazer a ponte entre o seu sistema e a interface do componente importado. Exemplo:

```javascript
// Código de Cola chamando um componente baixado
import { validarCPF } from 'validador-cpf';

// Conecta na interface
if (validarCPF(cpfDoCliente)) {
  // Executa a lógica do sistema com base na resposta do componente
}
```

## Decisão arquitetural: "tanque de guerra" x "patinete elétrico"

Complementando o que já foi registrado sobre contêineres de middleware: na escolha da infraestrutura para rodar componentes, aplica-se o conceito de trade-off (análise de prós e contras onde não existe solução perfeita, apenas a mais adequada ao contexto).

- **Contêiner de middleware pesado** (ex.: EJB tradicional) — o "tanque de guerra": recursos empresariais nativos e ultra robustos, mas alto consumo de memória RAM, inicialização lenta e alta complexidade.
- **Serviço Web/biblioteca leve** (ex.: API REST) — o "patinete elétrico": leveza, inicialização em milissegundos e extrema agilidade, mas exige implementação manual se forem necessários recursos empresariais complexos.

**Regra prática:** usar um contêiner de middleware corporativo pesado para executar uma função simples (como conversão de moeda) equivale a usar um tanque de guerra para ir à padaria. A decisão arquitetural correta escolhe a ferramenta proporcional ao tamanho do problema.