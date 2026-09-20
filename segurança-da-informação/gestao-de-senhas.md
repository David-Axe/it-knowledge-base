# Gestão de Senhas

**Fonte:** Estudonauta (curso com Gustavo Guanabara e Alfredo)
**Data:** 20/09/2026

## Reuso de Senhas (Credential Stuffing)

Usar a mesma senha em múltiplos serviços cria um ponto único de falha: se um serviço secundário (com segurança mais fraca) for comprometido, a mesma credencial pode ser testada em contas críticas, como bancos e e-mails — esse ataque de testar credenciais vazadas em massa em outros serviços é chamado de *Credential Stuffing* (algo como "recheio de credenciais").

## Gerenciadores de Senhas

Solução que mitiga a limitação natural da memória humana de guardar muitas senhas complexas. Permitem gerar senhas aleatórias, longas e exclusivas para cada serviço, armazenando-as em um cofre criptografado, acessível apenas por uma senha-mestra ou chave de criptografia.