# Manutenção de banco de dados

Data: 31/10/2026 | Fonte: Faculdade ADS

Rotinas preventivas que mantêm o banco íntegro, rápido e recuperável. Fazem parte das responsabilidades do DBA descritas em [[banco-de-dados/README|banco de dados]].

- **[[backup|Backup]] (cópia de segurança):** criação periódica de cópias dos arquivos físicos do banco, para permitir a recuperação diante de desastres.
- **Aspiração (*vacuum*, "aspirar"):** processo, como no PostgreSQL, que recupera e reutiliza o espaço em disco ocupado por linhas excluídas ou atualizadas, e atualiza as estatísticas usadas na otimização de consultas.
- **Reindexação (*reindex*):** recupera páginas de índice em árvore (*B-Tree*, "árvore B") que ficaram vazias após exclusões, mantendo o desempenho das buscas.
- **Gestão de [[logs]] (registros):** monitoramento e rotação automática dos arquivos de log, para auditar transações e diagnosticar erros de forma controlada.