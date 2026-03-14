---
order: 1
name: find-news
title: "Buscar Notícias Cripto"
agent: roberto-radar
---

# Task: Buscar Notícias Cripto

## Purpose
Pesquisar e coletar 15-20 candidatos de notícias cripto das últimas 72 horas, abrangendo mercado brasileiro e internacional, com foco em temas relevantes para o público da EAZ Educação (arbitragem, DeFi, regulação, Bitcoin, altcoins).

## Process

### Passo 1: Ler o foco de pesquisa
Ler o arquivo `squads/eaz-social/output/research-focus.md` para entender os temas prioritários definidos no checkpoint anterior. Se o arquivo não existir, usar os temas padrão: Bitcoin, DeFi, regulação cripto Brasil, arbitragem.

### Passo 2: Executar buscas por tema
Para cada tema prioritário, executar buscas web com as seguintes estratégias:

**Mercado BR:**
- `"Bitcoin" OR "cripto" site:mercadobitcoin.com.br OR site:foxbit.com.br`
- `"criptomoedas" "Brasil" "CVM" OR "Banco Central" -novela -futebol`
- `"arbitragem cripto" OR "DeFi" "reais" OR "BRL" últimas 72 horas`

**Internacional com impacto BR:**
- `"Bitcoin" "price" OR "ETF" site:coindesk.com OR site:cointelegraph.com`
- `"DeFi" "TVL" OR "protocol" site:defillama.com OR site:theblock.co`
- `"regulation" "crypto" "SEC" OR "EU" OR "Brazil" últimas 48 horas`

**Fontes prioritárias a consultar:**
- CoinDesk (coindesk.com)
- CoinTelegraph Brasil (br.cointelegraph.com)
- Mercado Bitcoin Blog (mercadobitcoin.com.br/blog)
- The Block (theblock.co)
- Decrypt (decrypt.co)
- CriptoFácil (criptofacil.com)
- Portal do Bitcoin (portaldobitcoin.uol.com.br)

### Passo 3: Coletar e catalogar resultados
Para cada notícia encontrada, registrar:
- Título completo
- URL da fonte
- Nome da publicação
- Data de publicação (verificar data original, não de compartilhamento)
- Resumo de 1-2 frases do conteúdo
- Nível de confiança (Alta/Média/Baixa)
- Tema principal (Regulação / DeFi / Bitcoin-Altcoins / Mercado BR / Macro)

Descartar notícias com mais de 7 dias (exceto se marcadas como contexto histórico relevante).

## Output Format

Salvar em `squads/eaz-social/output/news-stories.md` com a seguinte estrutura:

```markdown
# Notícias Coletadas — [DATA]

## Resumo da Coleta
- Total coletado: X notícias
- Período coberto: últimas 72h
- Fontes consultadas: X publicações

## Candidatos

### [Número]. [Título da Notícia]
- **Fonte:** [Nome da publicação]
- **URL:** [link completo]
- **Data:** DD/MM/AAAA HH:MM
- **Acesso em:** DD/MM/AAAA
- **Tema:** [categoria]
- **Confiança:** Alta / Média / Baixa
- **Resumo:** [1-2 frases descrevendo o conteúdo factual]
- **Impacto BR:** [1 frase sobre relevância para investidor brasileiro]
```

## Output Example

```markdown
# Notícias Coletadas — 14/03/2026

## Resumo da Coleta
- Total coletado: 17 notícias
- Período coberto: últimas 72h
- Fontes consultadas: 8 publicações

## Candidatos

### 1. Bitcoin supera US$ 95.000 após aprovação de ETF de opções pela SEC
- **Fonte:** CoinDesk
- **URL:** https://coindesk.com/markets/2026/03/14/bitcoin-95000-sec-options-etf
- **Data:** 14/03/2026 09:30
- **Acesso em:** 14/03/2026
- **Tema:** Bitcoin-Altcoins
- **Confiança:** Alta
- **Resumo:** A SEC aprovou formalmente o primeiro ETF de opções sobre Bitcoin nos EUA, levando o BTC a superar US$ 95.000 pela primeira vez em 3 meses com volume acima de US$ 42 bilhões em 24h.
- **Impacto BR:** Alta relevância — movimento impacta diretamente preço em reais e pode aumentar interesse de investidores pessoa física brasileiros.

### 2. CVM publica nova regulamentação para exchanges de cripto no Brasil
- **Fonte:** Portal do Bitcoin
- **URL:** https://portaldobitcoin.uol.com.br/cvm-regulamentacao-exchanges-2026
- **Data:** 13/03/2026 15:45
- **Acesso em:** 14/03/2026
- **Tema:** Regulação
- **Confiança:** Alta
- **Resumo:** A CVM publicou instrução normativa exigindo que exchanges registradas no Brasil mantenham reservas de 100% dos ativos dos clientes em custódia segregada, com prazo de adequação de 180 dias.
- **Impacto BR:** Impacto direto e imediato — afeta todas as exchanges operando no Brasil, pode gerar movimentação de usuários entre plataformas.

### 3. Uniswap V4 atinge US$ 8 bilhões em TVL em 30 dias após lançamento
- **Fonte:** The Block
- **URL:** https://theblock.co/post/uniswap-v4-tvl-8-billion
- **Data:** 13/03/2026 11:20
- **Acesso em:** 14/03/2026
- **Tema:** DeFi
- **Confiança:** Alta
- **Resumo:** Uniswap V4 atingiu US$ 8 bilhões em valor total bloqueado (TVL) em apenas 30 dias desde o lançamento, superando a versão anterior no mesmo período e gerando US$ 12 milhões em taxas para provedores de liquidez.
- **Impacto BR:** Relevância média — oportunidade educacional sobre DeFi e geração de renda passiva via liquidity providing.

### 4. Mercado Bitcoin registra volume recorde de R$ 2,3 bilhões em fevereiro
- **Fonte:** CoinTelegraph Brasil
- **URL:** https://br.cointelegraph.com/news/mercado-bitcoin-volume-record-fevereiro-2026
- **Data:** 12/03/2026 14:00
- **Acesso em:** 14/03/2026
- **Tema:** Mercado BR
- **Confiança:** Alta
- **Resumo:** A Mercado Bitcoin divulgou relatório com volume de negociação de R$ 2,3 bilhões em fevereiro de 2026, crescimento de 47% em relação ao mesmo mês de 2025, puxado principalmente por BTC e ETH.
- **Impacto BR:** Alta relevância — demonstra crescimento do mercado local e interesse crescente do investidor brasileiro.

### 5. Arbitragem entre Binance e Mercado Bitcoin atinge spread de 2,8% no BTC
- **Fonte:** CriptoFácil
- **URL:** https://criptofacil.com/arbitragem-binance-mercado-bitcoin-spread-marco-2026
- **Data:** 14/03/2026 08:15
- **Acesso em:** 14/03/2026
- **Tema:** Mercado BR
- **Confiança:** Média
- **Resumo:** Análise técnica identificou spread de arbitragem de até 2,8% entre cotação do Bitcoin na Binance Internacional e Mercado Bitcoin, acima da média histórica de 1,2%, possivelmente relacionado ao anúncio regulatório da CVM.
- **Impacto BR:** Alta relevância direta para público EAZ — tema central da proposta de valor da empresa.
```

## Quality Criteria
- [ ] Mínimo de 15 candidatos coletados
- [ ] Cada item contém todos os 7 campos obrigatórios (título, fonte, URL, data, tema, confiança, resumo)
- [ ] No máximo 3 notícias da mesma publicação no total
- [ ] Pelo menos 1 notícia de cada tema: Regulação, DeFi, Bitcoin-Altcoins, Mercado BR
- [ ] Todas as datas verificadas como publicação original (não republicação)
- [ ] Pelo menos 60% dos itens com confiança Alta ou Média

## Veto Conditions
- **VETO se** menos de 10 notícias verificáveis forem encontradas (resultados insuficientes para seleção editorial adequada)
- **VETO se** mais de 50% dos itens tiverem confiança Baixa (qualidade de fontes inadequada)
- **VETO se** todas as notícias forem de apenas 1-2 publicações (diversidade de fontes insuficiente)
