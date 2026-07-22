# Prompt-molde: site interativo "cair o queixo" (estilo Dalila)

Cole o bloco abaixo numa conversa nova, trocando os campos entre colchetes
`[assim]` pelo do novo projeto. Quanto mais específico você for nos campos,
mais fiel fica ao pedido original.

---

## PROMPT

Crie um site interativo, totalmente tecnológico, estilo "central de comando",
para apresentar **[NOME DO PRODUTO/PROJETO]** para **[PÚBLICO — ex: meu gestor,
um cliente, investidores]**. Use a identidade visual de **[MARCA]**
(cor principal `[HEX]`, se não tiver marca definida use um acento único sobre
fundo escuro neutro).

### Estrutura de seções (nessa ordem)

1. **Nav fixa** com blur, logo + links âncora para cada seção + botão CTA amarelo.
2. **Hero em tela cheia** com:
   - Fundo: canvas de "rede neural" animada (pontos conectados por linhas finas,
     reagindo ao mouse) + vídeo de fundo em loop (se houver) + overlay escuro
     gradiente pra manter o texto legível + grid pontilhado sutil.
   - Eyebrow com ponto pulsante (`● SISTEMA X · Y`).
   - Título grande (H1) com 2-3 frases-chave marcadas como **interativas**:
     sublinhado pontilhado, brilho ao passar o mouse, e **tooltip explicando
     o significado** daquela frase ao hover/toque.
   - Efeito cinematográfico: só a simulação/demo aparece primeiro; depois de
     ~2-3s o título entra **palavra por palavra**, com blur→foco, leve escala
     e deslocamento vertical perceptível (30-40px, não sutil).
   - Métricas com contador crescente (count-up) ao entrar na tela.
   - Ao lado do texto: uma **simulação ao vivo** (ex: chat digitando uma
     conversa real do produto, com indicador de "digitando...", mensagens
     aparecendo em sequência, e loop automático a cada N segundos).
3. **Ticker horizontal** com frases-chave rolando infinitamente.
4. **Contador ao vivo com meta**: número grande que sobe devagar e aleatoriamente
   (ex: a cada 6-15s), rótulo do que está sendo contado, número da meta ao lado,
   barra de progresso proporcional com %, e ao bater a meta: flash de destaque
   + mensagem de celebração + **reinício automático do ciclo** (zera e recomeça).
5. **Diagrama de arquitetura interativo**: nós conectados ao núcleo central por
   linhas, com "pacotes de dados" (partículas) viajando pelas conexões em loop.
   Clicar/passar o mouse num nó destaca a conexão e mostra detalhes num painel
   ao lado (nome, papel, descrição).
6. **Grid de capacidades em bento** (cards de tamanhos variados, alguns wide/tall)
   com ícone, título e descrição — efeito de spotlight que segue o mouse dentro
   de cada card.
7. **Simulador interativo**: critérios clicáveis (checkbox estilizado) que
   alimentam um gauge circular animado (SVG, `stroke-dashoffset`) mostrando uma
   pontuação/resultado que muda em tempo real, com veredito textual junto.
8. **Linha do tempo/fluxo** em 4 passos numerados, conectados por uma linha
   horizontal, com hover ou reveal-on-scroll.
9. **CTA final** com borda e glow na cor de destaque, dois botões (ação
   primária + secundária).
10. **Footer** com logo, descrição curta, links e copyright.

### Regras técnicas obrigatórias

- **Sem frameworks/CDNs externos** — tudo em HTML+CSS+JS puro num único arquivo
  (funciona em GitHub Pages sem build).
- **Tema escuro** (`#07070a`/`#0c0c11`) com **uma única cor de destaque** (nunca
  duas), neutros de baixa saturação, tipografia com um par: uma display
  (personalidade, ex: Space Grotesk/Quicksand) + uma de leitura (Inter) + uma
  mono para dados (JetBrains Mono).
- Toda animação de entrada usa `reveal-on-scroll` via `IntersectionObserver`
  (fade + translateY), **exceto** o header (que roda em `scroll` simples) e o
  contador/chat (que rodam por timers próprios).
- Respeitar `prefers-reduced-motion: reduce` — desligando toda animação nesse caso.
- Fundo de rede neural: `<canvas>` fixo, `requestAnimationFrame`, pontos com
  velocidade própria, atração leve ao mouse, linhas entre pontos próximos com
  opacidade proporcional à distância.
- Escrever todo o copy em **português do Brasil**, tom direto e próximo
  (segunda pessoa, "você"), sem jargão técnico desnecessário.
- Ao final, testar no navegador local (server HTTP simples) antes de publicar,
  conferindo console de erros.

### Publicação

Depois de pronto, criar um repositório novo no GitHub (`gh repo create`),
subir o `index.html` na raiz e ativar GitHub Pages via API
(`gh api -X POST repos/OWNER/REPO/pages -f "source[branch]=main" -f "source[path]=/"`),
retornando o link final `https://OWNER.github.io/REPO/`.

---

## Campos para preencher antes de colar

- `[NOME DO PRODUTO/PROJETO]`: 
- `[PÚBLICO]`: 
- `[MARCA]` / `[HEX]`: 
- Métricas do hero (4 números): 
- Roteiro da conversa/demo simulada: 
- Agentes/módulos do diagrama de arquitetura (nome + papel + descrição de cada um): 
- Critérios do simulador de pontuação: 
- Texto do contador ao vivo + valor inicial + meta: 
- Vídeo de fundo (se houver, caminho do arquivo): 
