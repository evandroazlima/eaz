# Anti-Padrões — EAZ Social Media Squad

Erros comuns a evitar em todo o conteúdo produzido pelo squad.
Derivados de análise de mercado, best practices do nicho cripto educacional e padrões da EAZ Educação.

---

## Anti-Padrões Críticos (Nunca Fazer)

### 1. Promessa de Lucro Garantido
**O erro:** "Ganhe R$ 5.000 por mês com arbitragem" | "Lucro garantido" | "Sem risco"
**Por que é perigoso:** Viola o CVM e pode caracterizar pirâmide ou fraude. Destrói a credibilidade da EAZ. Promessas irreais geram expectativas que frustram o aluno e prejudicam conversão real.
**Correto:** "Aprenda o método que me gerou consistência em arbitragem" | "Veja como opero na prática"

### 2. Dados de Mercado Inventados ou Desatualizados
**O erro:** Inventar porcentagens, citar preços de semanas atrás como "hoje", usar dados sem fonte.
**Por que é perigoso:** O público cripto verifica dados em tempo real. Uma informação errada destrói a autoridade do canal em segundos.
**Correto:** Usar apenas dados verificáveis. Se não tem dado atual, usar uma framework ou princípio em vez de número específico.

### 3. Conteúdo Evergreen Desconexo
**O erro:** "7 dicas para investir em cripto" sem ancoragem em evento atual.
**Por que é perigoso:** No nicho cripto, conteúdo sem contexto de mercado soa genérico. O algoritmo e o público preferem conteúdo que responde à situação atual do mercado.
**Correto:** Sempre ancorar o conteúdo em notícia ou dado atual, mesmo que o ensinamento seja atemporal. "Com BTC em queda de 8%, aqui estão 7 princípios que uso..."

### 4. Tom de FOMO Manipulador
**O erro:** "ÚLTIMA CHANCE", "Vai perder a oportunidade da sua vida", "Em 24 horas acaba"
**Por que é perigoso:** O público educado em cripto (o público da EAZ) é altamente resistente a FOMO barato. Esse tom associa a EAZ a esquemas duvidosos.
**Correto:** Urgência baseada em dado real. "Esse spread costuma durar 10-30 minutos" é urgência real. "ÚLTIMA CHANCE" vazio é manipulação.

### 5. Jargão Técnico Sem Explicação
**O erro:** "A IV dos contratos de opções mostra sobrecompra na banda de bollinger"
**Por que é perigoso:** Aliena iniciantes (público maior) sem impressionar intermediários (que já sabem). Contradiz o posicionamento de acessibilidade da EAZ.
**Correto:** Explicar o jargão na mesma frase. "A volatilidade implícita (uma métrica de quanto o mercado espera que o preço varie) está elevada — o que cria oportunidades para quem opera opções."

---

## Anti-Padrões de Formato

### 6. Instagram — Hook depois do "ver mais"
**O erro:** Começar a legenda com "Nesse post vou falar sobre arbitragem. A arbitragem é uma estratégia que..."
**Por que é ruim:** Os primeiros 125 caracteres são tudo. Se o hook não está nesse espaço, o post já perdeu.
**Correto:** "BTC caiu 8% hoje. Para quem conhece arbitragem, isso é oportunidade — não pânico. Desliza. 👇"

### 7. Instagram — Slides com menos de 40 palavras sem justificativa
**O erro:** Slides com apenas "ARBITRAGEM: compra baixo, vende alto" — sem dado, sem contexto, sem suporte.
**Por que é ruim:** Superficial. Não entrega valor real. O algoritmo do Instagram penaliza carrosséis que não prendem atenção.
**Correto:** Cada slide tem headline + texto de suporte com dado, exemplo ou explicação. Mínimo 40 palavras.

### 8. YouTube — Intro com "Oi pessoal"
**O erro:** "Oi pessoal, bem-vindos de volta ao canal, hoje vou falar sobre..."
**Por que é ruim:** Os primeiros 30 segundos determinam o watch time. "Oi pessoal" é o sinal mais claro de que o vídeo não tem ritmo.
**Correto:** Começar com o valor imediato. "Bitcoin regulamentado no Brasil — o que isso muda na prática para quem opera. Deixa eu te mostrar."

### 9. YouTube — Múltiplos CTAs
**O erro:** "Curte, se inscreve, ativa o sininho, me segue no Instagram, entra no grupo, compra o curso, deixa comentário..."
**Por que é ruim:** Dilui cada CTA. O espectador não sabe o que fazer e não faz nada.
**Correto:** Um CTA único, no final, depois de entregar o valor. "Se isso foi útil, o próximo vídeo sobre tributação cripto vai mudar como você opera — link na descrição."

### 10. LinkedIn — Link no corpo do post
**O erro:** "Veja o artigo completo aqui: [link]"
**Por que é ruim:** O algoritmo do LinkedIn deprimioriza posts com links externos em até 3x. Nunca no corpo.
**Correto:** "Artigo completo no comentário 👇" — postar o link como primeiro comentário logo após publicar.

### 11. Reels — Sem legendas/subtítulos
**O erro:** Reels gravados apenas com áudio, sem texto na tela.
**Por que é ruim:** 85% dos usuários do Instagram assistem sem som. Um Reel sem legenda perde a maioria do alcance.
**Correto:** Especificar legenda burned-in em todos os momentos falados OU garantir que o texto na tela comunique o essencial mesmo sem som.

---

## Anti-Padrões de Design

### 12. Texto abaixo de 20px
**O erro:** Usar fontes de 14px, 16px, 18px em slides de Instagram.
**Por que é ruim:** Ilegível em tela de celular. Os slides ficam amontoados e a leitura não acontece.
**Correto:** Mínimo 34px para body, 43px para heading, 58px para hero em Instagram (1080x1440).

### 13. Contador de slides na imagem
**O erro:** "1/8", "Slide 2 de 10" incluído no design do slide.
**Por que é ruim:** Instagram já mostra navegação nativa. O contador cria poluição visual e deixa o slide parecer mais antigo.
**Correto:** Nunca incluir contador. Usar estrutura visual para indicar progressão (cores alternadas, numeração no conteúdo quando relevante).

### 14. Design com dependências externas
**O erro:** HTML que depende de Bootstrap CDN, JavaScript externo, imagens remotas.
**Por que é ruim:** Playwright não consegue renderizar dependências externas no momento da screenshot. O slide fica em branco ou quebrado.
**Correto:** CSS inline completo, Google Fonts via @import (único recurso externo permitido). Imagens como base64 ou paths absolutos locais.

---

## Anti-Padrões de Publicação

### 15. Publicar sem dry-run
**O erro:** Chamar a API de publicação direto sem testar.
**Por que é ruim:** Falhas silenciosas, credenciais expiradas, formato errado — tudo isso cria problemas reais (post com imagem errada, legenda cortada).
**Correto:** Sempre dry-run primeiro. Só publicar após aprovação explícita do usuário com o preview completo.

### 16. Adaptar o mesmo texto bruto para todas as plataformas
**O erro:** Copiar a legenda do Instagram e postar no LinkedIn sem adaptação.
**Por que é ruim:** Cada plataforma tem limitações de caracteres, convenções de hashtag, e expectativas de audiência completamente diferentes.
**Correto:** Cada formato tem sua própria versão adaptada pelo agente especialista.
