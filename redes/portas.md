# Portas

## [02/09/2026] | Fonte: Estudo autônomo (mentoria com IA)

Dentro do próprio dispositivo, os dados que chegam pelo endereço IP são direcionados a um software específico através de portas — uma espécie de subdivisão dentro do próprio IP, relativa a cada software instalado naquele dispositivo.

Existem portas definidas por convenção (chamadas de portas conhecidas), reservadas para tipos específicos de software — por exemplo, a porta 443 para navegação segura. E existem outras portas mais livres, que ficam disponíveis dependendo do software que as estiver utilizando no momento.

---

  

## Nova entrada — 08/09/2026 | Fonte: Estudo autônomo com IA

## Portas de rede

Uma porta é um identificador utilizado para direcionar comunicações a determinados serviços em um dispositivo. Um endereço pode ser representado combinando [[endereco-ip]] e porta, por exemplo: `192.168.56.102:80​`, onde "192.168.56.102" é o endereço IP e "80" é a porta.

**Relação com serviços:** uma máquina pode disponibilizar diferentes serviços através de diferentes portas — por exemplo, SSH na porta 22, HTTP na 80, HTTPS na 443.

**Esclarecimento importante:** encontrar uma porta aberta não significa que um sistema foi invadido. Significa apenas que existe um serviço acessível através daquela porta.

**Perspectiva de segurança:** em segurança da informação, conhecer quais portas e serviços estão disponíveis pode ser importante durante o reconhecimento de um sistema. O objetivo defensivo é compreender quais serviços estão expostos, quais são realmente necessários, quais precisam ser protegidos, e quais podem representar riscos — inclusive usando um [[scanner-de-portas]] para esse levantamento.