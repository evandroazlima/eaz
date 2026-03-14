---
order: 2
name: rank-stories
title: "Ranquear Histórias para Conteúdo"
agent: roberto-radar
---

# Task: Ranquear Histórias para Conteúdo

## Purpose
Avaliar os candidatos coletados na tarefa anterior e selecionar as 3-5 histórias com maior potencial de conteúdo para o público EAZ, gerando um ranking justificado com ângulo sugerido para cada história selecionada.

## Process

### Passo 1: Ler candidatos e critérios
Ler o arquivo `squads/eaz-social/output/news-stories.md` (gerado pela task find-news.md) e o arquivo `squads/eaz-social/pipeline/data/quality-criteria.md` para entender os critérios de avaliação da EAZ.

### Passo 2: Pontuar cada candidato
Para cada notícia candidata, calcular uma pontuação de 0-10 com base nos critérios:

**Relevância para público EAZ (0-3 pts):**
- 3 pts: Diretamente sobre arbitragem, DeFi renda passiva, ou regulação BR afetando investidores
- 2 pts: Bitcoin/altcoins com contexto de investimento acessível
- 1 pt: Macro cripto com conexão indireta ao investidor BR
- 0 pts: Notícia puramente técnica ou sem conexão com público iniciante/intermediário

**Potencial educacional (0-3 pts):**
- 3 pts: Permite ensinar um conceito claro com exemplo real e atual
- 2 pts: Reforça conceito já ensinado com dado novo
- 1 pt: Contexto de mercado útil mas sem gancho educacional óbvio
- 0 pts: Pouco potencial de aprendizado para o público

**Urgência/Frescor (0-2 pts):**
- 2 pts: Publicado nas últimas 24h, ainda em desenvolvimento
- 1 pt: Publicado entre 24-72h, ainda relevante
- 0 pts: Mais de 72h ou dado desatualizado

**Originalidade (0-2 pts):**
- 2 pts: Ângulo ainda não explorado por outros criadores de conteúdo cripto BR
- 1 pt: Tema popular mas com ângulo diferenciado possível
- 0 pts: Notícia amplamente coberta sem diferencial possível

### Passo 3: Selecionar e escrever ranking final
Selecionar as 3-5 histórias com maior pontuação (mínimo 6/10 para inclusão). Para cada história selecionada, escrever:
- Posição no ranking (1 = maior potencial)
- Dados completos da notícia
- Pontuação detalhada por critério
- Ângulo sugerido para conteúdo EAZ (1-2 frases descrevendo como usar a notícia)
- Formato recomendado (carrossel, reels, post único, thread)
- Tom recomendado (educacional calmo / urgência informativa / celebração / alerta)

## Output Format

Salvar em `squads/eaz-social/output/ranked-stories.md` com a seguinte estrutura:

```markdown
# Histórias Ranqueadas — [DATA]

## Critérios Aplicados
- Relevância para público EAZ (0-3)
- Potencial educacional (0-3)
- Urgência/Frescor (0-2)
- Originalidade (0-2)
- **Total máximo: 10 pontos**

## Top Stories

### #[Posição] — [Título]
**Pontuação: X/10**
- Relevância: X/3 — [justificativa em 1 frase]
- Educacional: X/3 — [justificativa em 1 frase]
- Frescor: X/2 — [justificativa em 1 frase]
- Originalidade: X/2 — [justificativa em 1 frase]

**Dados:**
- Fonte: [nome]
- URL: [link]
- Data: DD/MM/AAAA
- Confiança: Alta/Média/Baixa

**Resumo:** [2-3 frases do conteúdo factual]

**Ângulo EAZ sugerido:** [1-2 frases sobre como usar para conteúdo educacional]
**Formato recomendado:** [carrossel / reels / post / thread]
**Tom:** [educacional calmo / urgência informativa / celebração / alerta]
```

## Output Example

```markdown
# Histórias Ranqueadas — 14/03/2026

## Critérios Aplicados
- Relevância para público EAZ (0-3)
- Potencial educacional (0-3)
- Urgência/Frescor (0-2)
- Originalidade (0-2)
- **Total máximo: 10 pontos**

## Top Stories

### #1 — Arbitragem entre Binance e Mercado Bitcoin atinge spread de 2,8% no BTC
**Pontuação: 9/10**
- Relevância: 3/3 — Tema central da proposta de valor EAZ, diretamente sobre arbitragem
- Educacional: 3/3 — Permite ensinar como identificar e calcular spread de arbitragem com dado real e atual
- Frescor: 2/2 — Publicado hoje, spread ainda ativo segundo dados de mercado
- Originalidade: 1/2 — Tema popular mas o dado específico de 2,8% ainda não foi amplamente explorado

**Dados:**
- Fonte: CriptoFácil
- URL: https://criptofacil.com/arbitragem-binance-mercado-bitcoin-spread-marco-2026
- Data: 14/03/2026
- Confiança: Média

**Resumo:** Spread de 2,8% identificado entre Binance Internacional e Mercado Bitcoin, acima da média histórica de 1,2%. O movimento coincide com o anúncio regulatório da CVM publicado ontem, que pode estar gerando incerteza e desbalanceamento entre exchanges locais e internacionais.

**Ângulo EAZ sugerido:** Usar como caso de estudo prático — "Isso é exatamente o tipo de oportunidade que ensinamos a identificar. Veja como calcular se vale a pena após taxas."
**Formato recomendado:** Carrossel (slide 1: dado chamativo, slides 2-4: como calcular, slide 5: CTA para curso)
**Tom:** Educacional calmo com gancho de oportunidade

---

### #2 — CVM publica nova regulamentação para exchanges de cripto no Brasil
**Pontuação: 8/10**
- Relevância: 3/3 — Regulação brasileira afeta diretamente todos os investidores do público EAZ
- Educacional: 3/3 — Oportunidade de explicar o que é custódia segregada e por que protege o investidor
- Frescor: 1/2 — Publicado ontem, 13/03, ainda em repercussão mas não é breaking news
- Originalidade: 1/2 — Tema amplamente coberto mas ângulo "o que muda para você" ainda pouco explorado

**Dados:**
- Fonte: Portal do Bitcoin
- URL: https://portaldobitcoin.uol.com.br/cvm-regulamentacao-exchanges-2026
- Data: 13/03/2026
- Confiança: Alta

**Resumo:** CVM exige que exchanges registradas no Brasil mantenham 100% dos ativos em custódia segregada. Prazo de 180 dias para adequação. Medida visa proteger investidores em caso de insolvência da exchange, seguindo modelo europeu (MiCA).

**Ângulo EAZ sugerido:** "Boa notícia para quem investe no Brasil — entenda o que mudou e como isso protege seu dinheiro."
**Formato recomendado:** Post único + stories explicativos
**Tom:** Educacional calmo com viés de tranquilização

---

### #3 — Uniswap V4 atinge US$ 8 bilhões em TVL em 30 dias após lançamento
**Pontuação: 7/10**
- Relevância: 2/3 — DeFi é tema relevante para público EAZ mas mais avançado
- Educacional: 3/3 — Excelente gancho para ensinar TVL, liquidity providing e renda passiva em DeFi
- Frescor: 1/2 — Publicado ontem, ainda relevante
- Originalidade: 1/2 — Uniswap muito coberto, mas ângulo de renda passiva específico é diferenciado

**Dados:**
- Fonte: The Block
- URL: https://theblock.co/post/uniswap-v4-tvl-8-billion
- Data: 13/03/2026
- Confiança: Alta

**Resumo:** Uniswap V4 atingiu US$ 8B em TVL em 30 dias — crescimento 3x mais rápido que V3 no mesmo período. Provedores de liquidez geraram em média 4,2% de rendimento mensal nas pools mais ativas segundo dados da DeFiLlama.

**Ângulo EAZ sugerido:** "Enquanto o mercado olha pro preço, DeFi continua gerando renda. Entenda como US$ 8 bilhões estão trabalhando 24h por dia."
**Formato recomendado:** Reels curto (30-45s) com texto explicativo
**Tom:** Educacional com curiosidade/assombro
```

## Quality Criteria
- [ ] Entre 3 e 5 histórias ranqueadas (nem poucas nem muitas)
- [ ] Cada história tem pontuação detalhada por critério com justificativa
- [ ] Ângulo EAZ sugerido é específico para a notícia (não genérico)
- [ ] Histórias selecionadas cobrem pelo menos 2 temas diferentes
- [ ] Nenhuma história selecionada com pontuação abaixo de 6/10
- [ ] Formato e tom recomendados são coerentes com o conteúdo da notícia

## Veto Conditions
- **VETO se** menos de 3 histórias atingirem pontuação mínima de 6/10 (qualidade geral dos candidatos insuficiente — reiniciar task find-news.md com busca ampliada)
- **VETO se** qualquer história selecionada tiver nível de confiança Baixa como única fonte disponível
