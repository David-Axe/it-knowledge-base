# Autenticação Multifator (MFA / 2FA)

**Fonte:** Estudonauta (curso com Gustavo Guanabara e Alfredo)
**Data:** 20/09/2026

## Fatores de Autenticação

Uma autenticação em duas etapas (2FA) genuína exige a combinação de categorias distintas de prova de identidade, não apenas duas senhas:

1. **Algo que você sabe** — senha ou PIN.
2. **Algo que você tem** — um dispositivo físico ou chave de segurança.
3. **Algo que você é** — biometria (impressão digital, reconhecimento facial).

## Vulnerabilidade do SMS e E-mail

SMS e e-mail são considerados métodos fracos de segundo fator. O SMS é vulnerável ao **SIM Swapping** (sequestro do chip na operadora), à interceptação em redes SS7 (protocolo de sinalização usado por operadoras de telefonia) e a ataques em caixas postais de voz via VoIP (telefonia por internet). Já o e-mail, como segundo fator, depende diretamente da integridade da própria conta de e-mail — o que reforça por que ela é o ponto central de recuperação de identidade digital.

## Autenticadores Baseados em Tempo (TOTP)

Aplicativos autenticadores geram tokens temporários (*Time-based One-Time Password*, ou "senha única baseada em tempo") de forma offline, diretamente no dispositivo, eliminando a dependência de redes de telefonia e suas vulnerabilidades.

## Chaves de Segurança Físicas (FIDO2/WebAuthn)

Representam o padrão mais elevado de proteção. Além de exigir a posse física do token, o protocolo valida o domínio do site diretamente no navegador — por isso é imune a ataques de phishing direcionados: mesmo que a vítima seja enganada a acessar um site falso, a chave física não autentica em um domínio que não seja o legítimo.