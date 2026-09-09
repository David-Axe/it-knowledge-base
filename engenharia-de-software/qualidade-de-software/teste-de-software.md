# Teste de Software

Data: 08/09/2026 | Fonte: Faculdade ADS

O teste de software é uma atividade integrante do processo de desenvolvimento cujo objetivo principal é revelar e encontrar falhas para garantir a qualidade do produto final. Na Engenharia de Software, entende-se por qualidade o atendimento rigoroso aos [[diagramas-uml|requisitos levantados]]. O propósito do teste não é "provar que o software não tem erros" — o que é inviável na prática —, mas sim expor inconsistências e diminuir riscos antes da entrega.

**Níveis de Teste:**
* **Unitário:** Focado nas menores partes isoladas do sistema (funções, métodos, classes). Geralmente executado pelo próprio desenvolvedor.
* **Integração:** Verifica se as diferentes unidades testadas separadamente funcionam e se comunicam de forma correta quando unificadas.
* **Sistema:** Avalia a aplicação ou funcionalidade como um todo em um ambiente integrado, verificando aspectos funcionais e não funcionais (manualmente ou via automação).
* **Aceitação:** Etapa final, realizada com a presença ou validação do cliente/representante do negócio, visando confirmar que o que foi construído atende às expectativas e aos requisitos para liberação do sistema.

**Desenvolvimento Guiado por Testes (TDD):**
Técnica em que a escrita dos testes precede a codificação da funcionalidade. Funciona no ciclo **Red-Green-Refactor**:
1. **Red:** Escreve-se um teste para a funcionalidade futura, que inicialmente falha.
2. **Green:** Escreve-se o código mínimo necessário para fazer o teste passar.
3. **Refactor:** Otimiza-se a estrutura e a clareza do código mantendo o teste passando.

**Analogia topográfica — O teste antes do código:**
Escrever o teste antes de programar é como traçar o percurso de uma ferrovia sobre um mapa topográfico antes de iniciar a obra. O teste antecipado mapeia as dificuldades do terreno, as restrições e o comportamento esperado das rotinas. Isso evita a "divagação" na hora da escrita do código, garantindo que o desenvolvedor construa estritamente o necessário para atender aos requisitos sem desperdício de escopo.