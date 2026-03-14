---
id: step-03-ideation
type: agent
label: "Ivan Ideia — Gerar 5 Ângulos de Conteúdo"
agent: ivan-ideia
execution: inline
inputFile: squads/eaz-social/output/ranked-stories.md
outputFile: squads/eaz-social/output/content-angles.md
---

# Step: Geração dos 5 Ângulos de Conteúdo

O Ivan Ideia executa a task `generate-angles.md`:

- Ler a história #1 ranqueada pelo Roberto Radar
- Aplicar o framework dos 5 ângulos (Educacional, Prático, Histórico, Crítico, Inspiracional)
- Gerar 5 ângulos completos com Hook, Mensagem, Formato, Tom, Público ideal e CTA
- Salvar em `squads/eaz-social/output/content-angles.md`

## Veto Conditions

- VETO se menos de 5 ângulos forem gerados
- VETO se dois ou mais ângulos usarem o mesmo gancho emocional principal
- VETO se qualquer hook usar FOMO manipulador como motor principal
