---
id: step-02-research
type: agent
label: "Roberto Radar — Pesquisar e Ranquear Notícias"
agent: roberto-radar
execution: subagent
model_tier: powerful
inputFile: squads/eaz-social/output/research-focus.md
outputFile: squads/eaz-social/output/ranked-stories.md
---

# Step: Pesquisa e Ranking de Notícias

O Roberto Radar executa as duas tasks em sequência:

1. **find-news.md** — Buscar 15-20 candidatos de notícias cripto das últimas 72h, com foco no tema definido no checkpoint. Salvar em `squads/eaz-social/output/news-stories.md`.

2. **rank-stories.md** — Avaliar e ranquear as top 3-5 histórias por potencial de conteúdo para EAZ. Salvar em `squads/eaz-social/output/ranked-stories.md`.

## Veto Conditions

- VETO se menos de 10 notícias verificáveis forem encontradas
- VETO se menos de 3 histórias atingirem pontuação mínima de 6/10 no ranking
- VETO se qualquer história selecionada tiver apenas fontes de confiança Baixa
