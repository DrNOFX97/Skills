# Skills

Coleção pessoal de [skills do Claude Code](https://docs.claude.com/en/docs/claude-code/skills) — instruções reutilizáveis que empacotam um fluxo de trabalho específico (auditoria, geração de documentação, revisão, etc.) para invocar sob pedido em qualquer projeto.

Cada skill vive na sua própria pasta, com um `SKILL.md` (as instruções que o Claude segue) e um `README.md` curto (o que faz, para quem serve).

## Instalar uma skill

Copiar a pasta da skill para:

- `~/.claude/skills/<nome>/` — disponível em todos os projetos, só nesta conta/máquina.
- `.claude/skills/<nome>/` (dentro de um repositório) — disponível só nesse projeto, e viaja com o repo para quem o clonar.

Sem dependências nem instalação — são ficheiros de texto simples.

## Skills

| Skill | O que faz |
|---|---|
| [`readme-architect`](readme-architect/) | Analisa um repositório e cria ou reestrutura o `README.md` — deteta stack, versões, scripts, testes e arquitetura reais, gera badges e diagramas Mermaid, e nunca inventa informação que não consiga confirmar no repositório. |
