# Scanner de Portas

Data: 08/09/2026 | Fonte: Estudo autônomo com IA

## O que é

Um scanner de portas é uma ferramenta utilizada para verificar quais [[portas]] de rede estão acessíveis em determinado dispositivo ou serviço.

A partir disso, pode-se identificar quais serviços podem estar disponíveis.

## Exemplo conceitual

Imagine uma máquina com o [[endereco-ip]] "192.168.56.102".

Um scanner pode verificar diferentes portas:

- 22 → aberta
- 80 → aberta
- 443 → aberta

Isso pode indicar a existência de serviços como SSH, HTTP e HTTPS.

## O que um scanner faz

De forma simplificada:

1. envia determinadas requisições ou pacotes ao alvo;
2. observa as respostas;
3. interpreta essas respostas;
4. informa quais portas parecem estar abertas, fechadas ou filtradas.

## Scanner não significa invasão

Um scanner de portas não necessariamente invade um computador.

Ele pode simplesmente descobrir quais serviços estão acessíveis.

Isso corresponde a uma etapa de [[reconhecimento]].

## Ferramentas

Uma ferramenta conhecida para esse tipo de atividade é o [[nmap]].

O Nmap pode ser utilizado através do terminal e também possui uma interface gráfica chamada Zenmap.