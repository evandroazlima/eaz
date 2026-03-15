---
id: step-04-image
type: agent
label: "Valentina Visual — Gerar Imagens com Ideogram"
agent: valentina-visual
execution: inline
inputFile: squads/eaz-social/output/content-angles.md
outputFile: squads/eaz-social/output/images.md
---

# Step: Geração de Imagens com Ideogram

A Valentina Visual executa a task `generate-images.md`:

- Ler os 5 ângulos de conteúdo do Ivan Ideia
- Para cada ângulo, construir um prompt visual em inglês compatível com a identidade EAZ
- Determinar o `aspect_ratio` correto (1:1 para carrossel/post, 9:16 para reels/stories)
- Chamar a API do Ideogram (modelo V_2) para cada ângulo
- Salvar as URLs e prompts gerados em `squads/eaz-social/output/images.md`

## Veto Conditions

- VETO se menos de 4 de 5 imagens forem geradas com sucesso
- VETO se a `IDEOGRAM_API_KEY` não estiver disponível no `.env`
- VETO se o arquivo `content-angles.md` não existir ou estiver vazio
