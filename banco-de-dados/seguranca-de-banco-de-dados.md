# Segurança de banco de dados

Data: 04/11/2026 | Fonte: Faculdade ADS

A segurança de um banco de dados trata de controlar quem pode acessar o quê. É uma aplicação, ao universo do SGBD, do [[autenticacao-autorizacao|controle de acesso]].

## Modelos de controle de acesso

- **Controle de Acesso Discricionário (DAC, *Discretionary Access Control*):** é o modelo mais comum. Os privilégios (`SELECT`, `INSERT`, `UPDATE`, `DELETE` e `EXECUTE`, este último sobre rotinas como as de [[banco-de-dados/programacao-no-servidor|programação no servidor]]) são concedidos com `GRANT` ("conceder") e retirados com `REVOKE` ("revogar"), a usuários ou a papéis (*roles*), que são conjuntos de privilégios atribuídos a vários usuários de uma vez.
- **Controle de Acesso Obrigatório (MAC, *Mandatory Access Control*):** usado em ambientes altamente sigilosos, como o militar. O acesso depende da correspondência estrita entre o nível de classificação do objeto e o nível de autorização do usuário.

## Controles especiais

- **Inferência:** protege dados estatísticos agregados, para impedir que se descubra, a partir deles, dados individuais sigilosos.
- **Fluxo:** impede o vazamento indireto de dados restritos para objetos de menor proteção.
- **[[criptografia|Criptografia]]:** codifica o texto puro (*plaintext*) em texto cifrado (*ciphertext*), de modo que só quem tem a chave consiga lê-lo.

As views (visões), descritas em [[banco-de-dados/sql|SQL]], também ajudam, ao ocultar colunas e linhas sensíveis de quem não deve vê-las.