# Manutenção de banco de dados

Data: 31/10/2026 | Fonte: Faculdade ADS

Rotinas preventivas que mantêm o banco íntegro, rápido e recuperável. Fazem parte das responsabilidades do DBA descritas em [[banco-de-dados/README|banco de dados]].

- **[[backup|Backup]] (cópia de segurança):** criação periódica de cópias dos arquivos físicos do banco, para permitir a recuperação diante de desastres.
- **Aspiração (*vacuum*, "aspirar"):** processo, como no PostgreSQL, que recupera e reutiliza o espaço em disco ocupado por linhas excluídas ou atualizadas, e atualiza as estatísticas usadas na otimização de consultas.
- **Reindexação (*reindex*):** recupera páginas de índice em árvore (*B-Tree*, "árvore B") que ficaram vazias após exclusões, mantendo o desempenho das buscas.
- **Gestão de [[logs]] (registros):** monitoramento e rotação automática dos arquivos de log, para auditar transações e diagnosticar erros de forma controlada.

---

## Nova entrada — 04/11/2026 | Fonte: Faculdade ADS

## Ciclo de vida e operação do SGBD

**Processos do MySQL:**

- `mysql.server`: script que gerencia o serviço (iniciar e parar).
- `mysqld_safe`: monitora o servidor e registra os erros em log.
- `mysqld`: o *daemon* (processo que roda em segundo plano) principal do servidor.

**Estados de uma base de dados (como no SQL Server):** *online* (disponível), *offline* (desligada), *restoring* (sendo restaurada), *recovering* (em recuperação), *recovery pending* (recuperação pendente), *suspect* (suspeita, com possível dano) e *emergency* (emergência).

**Desligamento seguro:** o comando `SHUTDOWN`, em SGBDs como o SQL Server, encerra os logons, grava um *checkpoint* (ponto de verificação, que descarrega as alterações pendentes no disco), finaliza os processos pendentes e desliga o servidor de forma segura.

## Logs de transação: REDO e UNDO

Complementando a gestão de [[logs]] registrada acima: os registros em log sustentam duas propriedades das transações, a atomicidade e a durabilidade ([[acid]]).

- **UNDO (desfazer):** reverte as alterações de transações que não foram concluídas, garantindo a atomicidade (a transação acontece por inteiro ou não acontece).
- **REDO (refazer):** reaplica as alterações de transações já confirmadas, garantindo a durabilidade (o que foi confirmado não se perde).