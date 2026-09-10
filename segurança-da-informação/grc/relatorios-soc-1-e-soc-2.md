# Relatórios de Asseguração: SOC 1 e SOC 2

**10/09/2026 — Estudo autônomo (Gemini)**

## Essência do Conceito
Os relatórios SOC (Service Organization Control) são laudos de auditoria independentes (padrão AICPA) que atestam a confiabilidade dos controles internos de prestadores de serviços em nuvem (SaaS/Cloud) — o tipo de atestado formal citado como saída do ciclo de auditoria em [[iso-iec-27001-e-27002]].

## SOC 1 vs. SOC 2

| Relatório | Foco Principal | Aplicação |
| :--- | :--- | :--- |
| **SOC 1** | **Controles Financeiros** | Softwares que impactam o balanço e as demonstrações contábeis do cliente (ex: ERPs, folhas de pagamento). |
| **SOC 2** | **Segurança e Operação de TI** | Avaliação da infraestrutura SaaS com base nos *Trust Services Criteria*. Padrão ouro para vendas B2B. |

### Os 5 Princípios do SOC 2 (Trust Services Criteria)
1. **Segurança (Security):** (Obrigatório) Proteção contra acessos não autorizados.
2. **Disponibilidade (Availability):** Sistema acessível conforme o SLA.
3. **Integridade de Processamento (Processing Integrity):** Entrega correta de dados sem erros.
4. **Confidencialidade (Confidentiality):** Proteção de segredos de negócio.
5. **Privacidade (Privacy):** Tratamento adequado de dados pessoais.

## Modalidades: Type 1 vs. Type 2
- **Type 1 (Tipo 1) — *O Retrato*:** Avalia se os controles foram **adequadamente desenhados** em uma data específica.
- **Type 2 (Tipo 2) — *O Filme*:** Avalia se os controles **foram executados e funcionaram na prática** ao longo de um período (geralmente de 6 a 12 meses). É a modalidade mais exigida pelo mercado global.

## Aplicação Prática
Responder a questionários de segurança e reunir evidências para chegar a um relatório SOC é uma das atividades centrais do Analista de GRC Júnior (ver [[analista-grc-junior]]).