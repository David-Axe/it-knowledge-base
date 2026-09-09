# API

Data: 08/09/2026 | Fonte: Estudo autônomo com IA

## O que é

API significa Application Programming Interface (Interface de Programação de Aplicações).

Uma API é uma interface que define como um software pode se comunicar e interagir com outro software.

Uma forma simples de compreender:

«API é uma ponte/interface de comunicação entre sistemas de software.»

## API não é hardware

Uma API não é um equipamento físico, cabo ou dispositivo.

É um conceito de software.

Uma API normalmente está associada a um sistema que está sendo executado em um servidor e disponibiliza determinadas funcionalidades para outros sistemas.

## Analogia

Uma analogia útil é a de um restaurante:

- Cliente → aplicativo ou sistema que faz a solicitação;
- Garçom → API;
- Cozinha → sistema que processa a solicitação;
- Pedido → requisição;
- Comida entregue → resposta.

O cliente não precisa entrar na cozinha. Ele utiliza a interface oferecida pelo garçom.

Da mesma forma, um software não precisa acessar diretamente a implementação interna de outro sistema. Ele pode utilizar a API disponibilizada por esse sistema.

## API e protocolos

Uma API possui alguma semelhança conceitual com um protocolo porque ambos envolvem regras de comunicação.

Entretanto, não são a mesma coisa.

**Protocolo:** estabelece regras para comunicação. Exemplos: [[TCP-IP]], HTTP.

**API:** define a interface através da qual um software pode solicitar determinadas operações ou informações de outro software.

Portanto:

«Protocolo = regras de comunicação.»

«API = interface/regras de utilização de funcionalidades disponibilizadas por um software.»

## Exemplo

Uma API pode disponibilizar um endpoint:

`GET /usuarios/123`

Esse endpoint poderia significar:

«Retornar os dados do usuário 123.»

A resposta poderia ser enviada em JSON:

```json
{
    "nome": "João",
    "email": "joao@example.com"
}
```

## API e servidor

Uma API frequentemente está sendo executada em um servidor.

É importante diferenciar os conceitos:

- Servidor → computador/sistema que fornece um serviço.
- API → interface através da qual outros softwares podem interagir com esse serviço.

Assim, uma API pode estar hospedada em um servidor, mas API e servidor não são a mesma coisa.

## API e segurança

As APIs são importantes para segurança da informação porque representam pontos de comunicação entre sistemas.

Uma API precisa controlar, entre outras coisas, quem está fazendo a requisição, o que essa pessoa ou sistema pode fazer ([[Autenticação]] e [[Autorização]]), quais dados podem ser acessados e quais informações podem ser alteradas.

Uma falha de autorização, por exemplo, pode permitir que um usuário autenticado acesse informações que pertencem a outro usuário.