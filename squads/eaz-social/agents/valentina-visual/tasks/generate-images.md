# Task: Gerar Imagens com Nano Banana (Google Gemini) via MCP

## Objetivo
Gerar uma imagem por ângulo de conteúdo usando a MCP tool `nanobanana`, com prompt otimizado para cada tom emocional.

## Inputs
- `squads/eaz-social/output/{run_id}/content-angles.md` — 5 ângulos gerados pelo Ivan Ideia

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
{visual_concept}, dark navy blue background (#0A1628), gold accents (#D4AF37),
clean tech-finance aesthetic, abstract data visualization, no text, no people,
no logos, professional, modern, {tone_modifier}, high quality
```

**tone_modifier por tipo de ângulo:**
- Educacional: `clean diagram style, clear iconography, calm atmosphere, soft lighting`
- Prático-Aplicável: `dynamic data flow, tech interface elements, energetic, motion blur`
- Contexto Histórico: `timeline visual, gradient temporal depth, analytical, deep blue tones`
- Desconstrução Crítica: `high contrast, dramatic shadows, investigative mood, tension, dark atmosphere`
- Inspiração/Celebração: `golden light rays, upward momentum, bright gold accents, empowering, optimistic`

### 3. Determinar o aspect_ratio

| Formato do Ivan | Aspect Ratio |
|---|---|
| Carrossel | `1:1` |
| Reels | `9:16` |
| Stories | `9:16` |
| Post único | `1:1` |

### 4. Chamar a MCP tool para cada ângulo

Usar a MCP tool `nanobanana` para gerar cada imagem. Exemplo de chamada:

```
Tool: nanobanana/generate_image
Parameters:
  prompt: "abstract blockchain network visualization, dark navy blue background, gold data nodes, clean tech-finance aesthetic, no text, no people, professional, modern, dynamic data flow, high quality"
  aspect_ratio: "1:1"
  model: "pro"  (usar "flash" se quiser economizar; "pro" para melhor qualidade)
```

A tool retornará a URL da imagem gerada — salvar essa URL.

### 5. Salvar o output

Criar o arquivo `squads/eaz-social/output/{run_id}/images.md` com o seguinte formato:

```markdown
# Imagens Geradas — {data}
**Gerado por:** Valentina Visual (Nano Banana Pro via MCP)

## Ângulo 1: {nome do ângulo}
**Tipo:** Educacional Direto
**Formato:** Carrossel (1:1)
**Model:** nano-banana-pro
**URL:** https://...
**Prompt usado:**
> {prompt exato enviado ao Nano Banana}

---

## Ângulo 2: ...
```

Repetir para todos os 5 ângulos.

---

## Modelos Disponíveis

| Model | Qualidade | Custo | Usar quando |
|---|---|---|---|
| `pro` | Máxima (4K, thinking) | ~$0.24/img | Posts de maior destaque |
| `flash` | Alta | Menor | Volume, testes |
| `nano` | Boa | Mínimo | Rascunhos |

**Recomendação padrão:** `pro` para os 5 ângulos finais de produção.

---

## Tratamento de Erros

- Se a MCP tool retornar erro de autenticação: a `GEMINI_API_KEY` está inválida ou não foi carregada — reportar ao usuário
- Se a tool retornar erro de rate limit: aguardar 5 segundos e tentar novamente
- Se a imagem não for gerada após 2 tentativas: tentar com model `flash` e prompt simplificado (remover `tone_modifier`)
- Se 3 tentativas falharem para o mesmo ângulo: registrar `ERRO: não foi possível gerar imagem` no output e continuar para o próximo ângulo

## Veto Conditions

- VETO se menos de 4 de 5 imagens forem geradas com sucesso
- VETO se a MCP tool `nanobanana` não estiver disponível
- VETO se o arquivo `content-angles.md` não existir ou estiver vazio
