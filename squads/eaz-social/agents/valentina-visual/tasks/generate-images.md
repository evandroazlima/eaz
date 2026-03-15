# Task: Gerar Imagens com Ideogram

## Objetivo
Gerar uma imagem por ângulo de conteúdo usando a API do Ideogram, com prompt otimizado para cada tom emocional.

## Inputs
- `squads/eaz-social/output/{run_id}/content-angles.md` — 5 ângulos gerados pelo Ivan Ideia
- `.env` — contém `IDEOGRAM_API_KEY`

## Output
- `squads/eaz-social/output/{run_id}/images.md` — URLs e prompts de todas as imagens geradas

---

## Instruções de Execução

### 1. Ler os ângulos de conteúdo

Ler o arquivo `content-angles.md` do run atual e identificar para cada ângulo:
- **Tipo**: (Educacional, Prático, Histórico, Crítico, Inspiração)
- **Tom**: conforme campo "Tom:" do ângulo
- **Formato recomendado**: conforme campo "Formato:" (Carrossel = 1:1, Reels = 9:16, Post único = 1:1)

### 2. Construir o prompt para cada ângulo

Usar o template abaixo, adaptando para o tom de cada ângulo:

```
{visual_concept}, dark navy blue background, gold accents, clean tech-finance aesthetic,
abstract data visualization, no text, no people, professional, modern, {tone_modifier},
high quality, 4k
```

**tone_modifier por tipo de ângulo:**
- Educacional: `clean diagram style, clear iconography, calm atmosphere`
- Prático-Aplicável: `dynamic data flow, tech interface, energetic`
- Contexto Histórico: `timeline visual, gradient depth, analytical, deep blue tones`
- Desconstrução Crítica: `high contrast, dramatic shadows, investigative mood, tension`
- Inspiração/Celebração: `golden light, upward momentum, bright accents, empowering`

### 3. Determinar o aspect_ratio

| Formato do Ivan | aspect_ratio Ideogram |
|---|---|
| Carrossel | `ASPECT_1_1` |
| Reels | `ASPECT_9_16` |
| Stories | `ASPECT_9_16` |
| Post único | `ASPECT_1_1` |

### 4. Chamar a API do Ideogram para cada ângulo

Carregar a variável de ambiente:
```bash
source .env
```

Fazer a chamada para cada ângulo:
```bash
curl -s -X POST "https://api.ideogram.ai/generate" \
  -H "Api-Key: $IDEOGRAM_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "image_request": {
      "prompt": "PROMPT_AQUI",
      "aspect_ratio": "ASPECT_1_1",
      "model": "V_2",
      "magic_prompt_option": "AUTO"
    }
  }'
```

Extrair a URL da imagem do campo `response.data[0].url`.

### 5. Salvar o output

Criar o arquivo `squads/eaz-social/output/{run_id}/images.md` com o seguinte formato:

```markdown
# Imagens Geradas — {data}
**Gerado por:** Valentina Visual

## Ângulo 1: {nome do ângulo}
**Tipo:** Educacional Direto
**Formato:** Carrossel (1:1)
**URL:** https://...
**Prompt usado:**
> {prompt exato enviado ao Ideogram}

---

## Ângulo 2: ...
```

Repetir para todos os 5 ângulos.

---

## Tratamento de Erros

- Se a API retornar erro 401: a `IDEOGRAM_API_KEY` está inválida — reportar ao usuário
- Se a API retornar erro 429: rate limit atingido — aguardar 5 segundos e tentar novamente
- Se a URL da imagem não estiver acessível: tentar regenerar com prompt mais simples (remover `tone_modifier` e manter apenas o template base)
- Se 3 tentativas falharem para o mesmo ângulo: registrar `ERRO: não foi possível gerar imagem` no output e continuar para o próximo ângulo

## Veto Conditions

- VETO se menos de 4 de 5 imagens forem geradas com sucesso
- VETO se a `IDEOGRAM_API_KEY` não estiver disponível no ambiente
