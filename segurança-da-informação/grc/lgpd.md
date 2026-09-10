# Lei Geral de Proteção de Dados (LGPD - Lei nº 13.709/2018)

**10/09/2026 — Estudo autônomo (Gemini)**

## Essência do Conceito
Legislação brasileira que disciplina o tratamento de dados pessoais de pessoas físicas, garantindo transparência, segurança e respeito aos direitos fundamentais. É a lei específica que rege o pilar de Privacidade descrito em [[seguranca-vs-privacidade-vs-compliance]].

## Papéis no Ecossistema SaaS

```text
    [ TITULAR ]  ---- Pessoa física a quem os dados pertencem.
         |
         v
  [ CONTROLADOR ] ---- Cliente do SaaS (decide O QUE fazer com o dado).
         |
         v
   [ OPERADOR ]   ---- Fornecedor do SaaS (executa sob ordens do Controlador).
         |
         v
   [ ENCARREGADO / DPO ] ---- Canal de comunicação entre Controlador, Titulares e ANPD.
```

## Destaques de Aplicação em GRC
- **O Fornecedor de SaaS como Operador:** A empresa fornece o software em nuvem, mas as decisões sobre quais dados coletar pertencem ao cliente (Controlador).
- **Atendimento a Direitos do Titular:** Requisições de exclusão enviadas diretamente ao Operador devem ser redirecionadas ao Controlador, responsável por autorizar a ação.
- **Conflito de Bases Legais:** O direito do titular de pedir exclusão de dados não é absoluto. A Base Legal de "Cumprimento de Obrigação Legal ou Regulatória" autoriza o Controlador a reter dados trabalhistas/fiscais pelo tempo exigido por lei.

## Aplicação Prática
Entender esses papéis é essencial para o Analista de GRC Júnior (ver [[analista-grc-junior]]), que frequentemente precisa mapear em qual papel a empresa se enquadra ao responder questionários de segurança de clientes.