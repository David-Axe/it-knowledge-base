# Gestão de Riscos e Controles Internos

**10/09/2026 — Estudo autônomo (Gemini)**

## Essência do Conceito
A Gestão de Riscos e os Controles Internos formam a relação de **Causa e Efeito** (ou Perigo e Escudo) na operação de TI. Todo controle interno existe para mitigar pelo menos um risco mapeado.

## Os Dois Lados da Moeda

### Gestão de Riscos
- **O que é:** Processo de avaliar incertezas por **Probabilidade vs. Impacto**.
- **Tratamentos de Risco:** Mitigar (reduzir), Transferir (ex: seguro), Evitar (cancelar a ação) ou Aceitar (assumir risco baixo).
- **Problema que resolve:** Tira a empresa do escuro e previne prejuízos catastróficos não previstos.

### Controles Internos
- **O que é:** Regras, rotinas, travas técnicas e verificações para garantir que o risco seja contido.
- **Tipos de Controles:**
  - **Preventivos:** Evitam a ocorrência do incidente (ex: janelas de manutenção, revisão de código, MFA).
  - **Detectivos:** Identificam o incidente em tempo real (ex: alertas de login suspeito, monitoramento de logs).
  - **Corretivos:** Restauram a operação após a falha (ex: plano de *rollback*, backups).

## Conceito Destacado: Chave Física de Segurança (Hardware Key)
- **O que é:** Token físico de hardware (ex: YubiKey, baseado nos padrões FIDO2/WebAuthn) para autenticação de acesso.
- **Aplicação como Controle Preventivo:** Previne ataques de *phishing* e roubo de sessão em infraestruturas Cloud, pois a chave valida o domínio exato do site e exige toque físico do usuário para liberar o acesso.

> **Regra:** Remediação é sempre mais custosa que prevenção. O controle corretivo sem o preventivo expõe a empresa a indisponibilidades e perdas financeiras.

## Relação com outros conceitos
Faz parte da Tríade GRC, especificamente do pilar de Risco (ver [[grc]]).