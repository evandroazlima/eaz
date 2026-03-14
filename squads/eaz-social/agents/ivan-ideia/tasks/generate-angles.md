---
order: 1
name: generate-angles
title: "Gerar 5 Ângulos de Conteúdo"
agent: ivan-ideia
---

# Task: Gerar 5 Ângulos de Conteúdo

## Purpose
A partir da história #1 ranqueada pelo Roberto Radar, gerar 5 ângulos emocionais distintos para conteúdo no Instagram/YouTube da EAZ Educação, cada um com gancho, mensagem central, formato e recomendação editorial completos.

## Process

### Passo 1: Ler a história selecionada
Ler o arquivo `squads/eaz-social/output/ranked-stories.md` e extrair os dados da história ranqueada em #1:
- Título completo
- Resumo factual
- Ângulo EAZ sugerido pelo Roberto
- Dados verificados (percentuais, valores, datas)

Também ler `squads/eaz-social/pipeline/data/tone-of-voice.md` para garantir alinhamento com a voz da EAZ.

### Passo 2: Aplicar o framework dos 5 ângulos
Para cada um dos 5 ângulos padrão, desenvolver em sequência:

**Ângulo 1 — Educacional Direto**
- Foco: Explicar o conceito por trás da notícia para quem nunca ouviu falar
- Pergunta guia: "O que alguém que não sabe nada de cripto precisa entender sobre isso?"
- Tom alvo: Didático, acolhedor, sem jargão ou com jargão explicado

**Ângulo 2 — Prático-Aplicável**
- Foco: Mostrar o que o investidor pode fazer ou aprender com isso agora
- Pergunta guia: "Qual ação concreta ou aprendizado prático isso gera?"
- Tom alvo: Direto, orientado a ação, sem ser prescritivo sobre investimento

**Ângulo 3 — Contexto Histórico**
- Foco: Conectar o fato atual com padrões anteriores ou tendências maiores
- Pergunta guia: "Isso já aconteceu antes? O que podemos aprender com o passado?"
- Tom alvo: Reflexivo, analítico, com perspectiva temporal

**Ângulo 4 — Desconstrução Crítica**
- Foco: Questionar o que não está sendo dito ou o que a notícia não responde
- Pergunta guia: "O que a manchete não está contando? Qual é o outro lado?"
- Tom alvo: Investigativo, cético construtivo, intelectualmente honesto

**Ângulo 5 — Inspiração/Celebração**
- Foco: Celebrar aprendizado, avanço do mercado ou validação do investidor educado
- Pergunta guia: "O que isso significa para quem se preparou / está aprendendo?"
- Tom alvo: Celebrativo, empoderador, recompensador do esforço de aprender

### Passo 3: Escrever os 5 ângulos completos
Para cada ângulo, preencher todos os campos do template de output. Verificar antes de finalizar:
- Os 5 hooks são claramente diferentes entre si?
- Algum hook usa FOMO? Se sim, reescrever.
- Todos os dados citados são verificáveis na notícia?
- Pelo menos 2 formatos diferentes foram sugeridos?

## Output Format

Salvar em `squads/eaz-social/output/content-angles.md` com a seguinte estrutura:

```markdown
# Ângulos de Conteúdo — [TÍTULO DA NOTÍCIA]
**Data:** DD/MM/AAAA
**Gerado por:** Ivan Ideia

## Notícia Base
[Título e resumo de 2 frases da notícia usada]

---

## Ângulo 1: [Nome do Ângulo] — [Emoji]
**Tipo:** Educacional Direto

**Hook:**
> [Frase de abertura que para o scroll — máx. 2 linhas]

**Mensagem:** [A ideia central que o público vai aprender/sentir com este conteúdo]

**Formato:** [Carrossel / Reels 30s / Reels 60s / Post único / Thread]
**Tom:** [Didático / Direto / Reflexivo / Investigativo / Celebrativo]
**Público ideal:** [Iniciante / Intermediário / Avançado / Todos]
**Chamada para ação:** [O que queremos que o público faça ao final]
```

## Output Example

```markdown
# Ângulos de Conteúdo — Bitcoin supera US$ 95.000 após aprovação de ETF de opções
**Data:** 14/03/2026
**Gerado por:** Ivan Ideia

## Notícia Base
A SEC aprovou o primeiro ETF de opções sobre Bitcoin nos EUA, levando o BTC a superar US$ 95.000 com volume de US$ 42 bilhões em 24h — o maior volume em 90 dias.

---

## Ângulo 1: O Que é um ETF de Opções? — 📚
**Tipo:** Educacional Direto

**Hook:**
> "Bitcoin bateu US$ 95.000 hoje. Mas a notícia real não é o preço — é o que a SEC aprovou e por que isso muda tudo."

**Mensagem:** Explicar o que é um ETF de opções de Bitcoin de forma simples: como funciona, por que é diferente de um ETF spot, e o que significa para o mercado ter essa ferramenta disponível.

**Formato:** Carrossel (6-8 slides: slide 1 = hook, slides 2-5 = explicação passo a passo, slide 6 = resumo, slide 7 = CTA)
**Tom:** Didático, acolhedor — como explicar para um familiar curioso
**Público ideal:** Iniciante a Intermediário
**Chamada para ação:** "Salva esse carrossel pra explicar pro seu amigo que ficou confuso com essa notícia"

---

## Ângulo 2: O Que Você Pode Fazer Com Isso Agora — ⚡
**Tipo:** Prático-Aplicável

**Hook:**
> "ETF de opções aprovado. Volume de US$ 42 bilhões. 3 perguntas que você precisa saber responder antes de qualquer movimento."

**Mensagem:** Guiar o investidor por 3 perguntas práticas de avaliação: (1) Isso muda minha tese de longo prazo? (2) Qual minha exposição atual ao BTC? (3) Esse é o tipo de aprovação que tende a ser sustentada historicamente? Foco em processo de tomada de decisão, não em conselho de compra/venda.

**Formato:** Reels 45s (ritmo rápido, 3 perguntas em tela com resposta verbal)
**Tom:** Direto, orientado a processo, sem alarme
**Público ideal:** Intermediário
**Chamada para ação:** "Comenta aqui qual dessas 3 perguntas você ainda não sabe responder — vou criar conteúdo sobre isso"

---

## Ângulo 3: Isso Já Aconteceu Antes — 🕰️
**Tipo:** Contexto Histórico

**Hook:**
> "Em 2024, quando o ETF spot de Bitcoin foi aprovado, o preço caiu 15% nas semanas seguintes. O que mudou desta vez — e o que continua igual."

**Mensagem:** Comparar com a aprovação do ETF spot em janeiro de 2024 — o que se repetiu (euforia inicial, volume alto), o que é diferente (produto mais sofisticado, mercado mais maduro, base de investidores institucionais maior). Objetivo: dar perspectiva histórica sem predição de preço.

**Formato:** Carrossel comparativo (antes vs. agora, slide a slide)
**Tom:** Analítico, perspectiva temporal, intelectualmente honesto sobre incertezas
**Público ideal:** Intermediário a Avançado
**Chamada para ação:** "Você estava no mercado em 2024? Conta nos comentários o que você fez diferente desta vez"

---

## Ângulo 4: O Que a Manchete Não Está Contando — 🔍
**Tipo:** Desconstrução Crítica

**Hook:**
> "Todo mundo está celebrando o ETF de opções. Mas ninguém está falando sobre o que acontece quando as opções vencem em massa. Vamos lá."

**Mensagem:** Explicar o fenômeno de "max pain" e "gamma squeeze" em mercados de opções — o que pode acontecer quando grandes posições vencem, como isso pode criar volatilidade mesmo em mercados "aprovados" por reguladores. Não é doom e gloom: é educação sobre mecânica de mercado que a maioria dos investidores não entende.

**Formato:** Reels 60s (mais denso, tom de bastidores)
**Tom:** Investigativo, cético construtivo — "existe um outro lado e vamos entendê-lo"
**Público ideal:** Intermediário a Avançado
**Chamada para ação:** "Segue o canal pra quando eu publicar o conteúdo completo sobre gamma squeeze — esse é o conceito que separa o investidor comum do preparado"

---

## Ângulo 5: Parabéns, Você Estava Certo — 🎉
**Tipo:** Inspiração/Celebração

**Hook:**
> "Há 2 anos, falar que Bitcoin teria ETF de opções regulamentado nos EUA parecia ficção científica. Hoje é notícia. O que mais parece 'impossível' hoje que vai ser normal em 2028?"

**Mensagem:** Celebrar a evolução do mercado cripto como validação do investidor que estudou, acreditou no processo e não saiu durante a volatilidade. Conectar com a jornada do público EAZ — "vocês aprenderam sobre isso aqui, antes de ser mainstream."

**Formato:** Post único + stories sequenciais com pergunta para audiência
**Tom:** Celebrativo, empoderador, retrospectivo com olhar para o futuro
**Público ideal:** Todos — especialmente quem acompanha a EAZ há mais tempo
**Chamada para ação:** "Marca aquele amigo que você tentou convencer sobre cripto e que não acreditou. Hoje é um bom dia pra mostrar."
```

## Quality Criteria
- [ ] Exatamente 5 ângulos gerados com os tipos: Educacional, Prático, Histórico, Crítico, Inspiracional
- [ ] Cada ângulo tem todos os 6 campos preenchidos: Hook, Mensagem, Formato, Tom, Público ideal, CTA
- [ ] Os 5 hooks são claramente distintos — nenhum começa da mesma forma ou usa o mesmo gancho emocional
- [ ] Nenhum hook usa FOMO direto ("não perca", "última chance", "todo mundo está comprando")
- [ ] Pelo menos 2 formatos diferentes sugeridos (ex: carrossel + reels)
- [ ] Todos os dados citados nos hooks são verificáveis na notícia de base

## Veto Conditions
- **VETO se** menos de 5 ângulos forem gerados (o framework exige exatamente 5 perspectivas distintas)
- **VETO se** dois ou mais ângulos usarem o mesmo gancho emocional principal (ex: dois ângulos de curiosidade ou dois de alerta)
- **VETO se** qualquer hook usar FOMO manipulador como motor principal de engajamento
