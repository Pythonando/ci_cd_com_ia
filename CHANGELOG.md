## [2026-06-24] - teste 10
**PR:** #10 por @Pythonando

### O que mudou
O projeto passou a contar com automação inteligente usando o Claude (IA da Anthropic) diretamente no fluxo de desenvolvimento. Agora, toda vez que um pull request é aberto, a IA revisa automaticamente o código, aponta possíveis problemas e até gera testes quando necessário. Além disso, ao mencionar `@claude` em comentários de issues ou PRs, a IA responde e executa tarefas. Por fim, quando um PR é aprovado e mergeado, as notas de lançamento são geradas automaticamente no CHANGELOG — como esta entrada aqui.

### Detalhes técnicos
- **`.github/workflows/claude-code-review.yml`**: Workflow com dois jobs: (1) revisão automática de código via `/code-review` para PRs abertos por membros/owners/collaborators, com geração automática de testes pytest commitados diretamente na branch do PR; (2) geração de release notes no CHANGELOG.md ao merge, com commit e push automático na branch base.
- **`.github/workflows/claude.yml`**: Workflow que aciona o Claude em resposta a menções `@claude` em comentários de issues, PRs e reviews.
- **`.github/workflows/claude-review-schema.json`**: Schema JSON que define o formato de saída estruturado da revisão (`has_critical_issues`, `risk_level`, `summary`).
- **`.claude/settings.json`**: Configuração de permissões do Claude Code para operações de escrita de arquivos e comandos git.
- **`app.py`**: Arquivo de script Python criado para fins de teste.

---
