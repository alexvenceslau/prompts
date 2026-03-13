Create ONE complete HTML file (index.html) — a vehicle protection landing page.

## BRAND IDENTITY

- Name: SuaProteção Veicular
- Tagline: "Melhor que seguro, sem burocracia"
- Main value proposition: "Proteção Veicular a partir de R$ 2,46/dia"
- Tone: direct, confident, accessible, jargon-free

---

## COLOR PALETTE & TYPOGRAPHY

### Base Colors

- Background primary: #000000
- Background secondary: #0a0f0c
- Background cards: #0f1a13
- Background elevated: #152b1c
- Surface border: rgba(28, 156, 75, 0.15)
- Body text: #EEEEEE
- Muted text: #888888

### Accent & Brand Colors

- Green primary: #1C9C4B
- Green secondary: #17803d
- Green light: #25c45e
- Green glow: rgba(28, 156, 75, 0.18)
- White accent: #FFFFFF
- Success: #22c55e
- Error: #ef4444

### Gradients

- Hero: linear-gradient(135deg, #000000 0%, #060d08 40%, #0d1f12 70%, #152b1c 100%)
- Green shimmer (for H1): linear-gradient(90deg, #17803d 0%, #1C9C4B 40%, #a8f0c2 60%, #1C9C4B 80%, #17803d 100%)
- Card hover overlay: linear-gradient(135deg, rgba(28,156,75,0.06) 0%, transparent 100%)
- Button: linear-gradient(135deg, #1C9C4B 0%, #17803d 100%)
- Button hover: linear-gradient(135deg, #25c45e 0%, #1C9C4B 100%)

### Typography

- Google Fonts: import both Montserrat (weights 400,700,900) + Inter (weights 400,500) via single @import
- Headings (H1, H2, H3): Montserrat, font-weight 900
- Body / paragraphs: Inter, font-weight 400
- Labels / badges / buttons: Montserrat, font-weight 700
- H1 size: clamp(2.2rem, 5vw, 4rem) — fluid responsive, no fixed breakpoints
- H2 size: clamp(1.6rem, 3.5vw, 2.6rem)
- H1 effect: background-clip text with green shimmer gradient (webkit-background-clip: text, color: transparent)
- Letter spacing headings: -0.02em
- Line height body: 1.7
- Apply native CSS text-wrap to all headings and body text:
  h1, h2, h3 { text-wrap: balance; } — evenly distributes words across lines, eliminates orphaned words
  p, li, blockquote { text-wrap: pretty; } — prevents lone words on the last line of paragraphs

### Buttons

- Primary: background linear-gradient(135deg, #1C9C4B, #17803d), color #FFFFFF, border: none, border-radius: 8px
- Primary hover: brightness(1.15), transform: translateY(-2px), box-shadow: 0 8px 30px rgba(28,156,75,0.45)
- Outline variant: background transparent, border: 1.5px solid #1C9C4B, color #1C9C4B
- Outline hover: background rgba(28,156,75,0.08)
- All buttons: font-family Montserrat, font-weight 700, letter-spacing 0.03em, transition all 0.3s ease

### Modern Effects

- Glassmorphism cards: background rgba(255,255,255,0.02), backdrop-filter blur(12px), border 1px solid rgba(28,156,75,0.18)
- Glow on active/hover elements: box-shadow 0 0 24px rgba(28,156,75,0.3)
- Subtle noise texture on hero via CSS pseudo-element ::before with SVG data URI turbulence filter, opacity 0.03
- Section dividers: use a full-width SVG wave shape as divider between sections
  (inline SVG with viewBox="0 0 1440 60", path with smooth bezier curve, fill color matching the next section's background)
  Each wave is unique — alternate direction (flip horizontally via transform: scaleX(-1)) between sections for visual rhythm.
  No horizontal lines, no borders. Sections flow into each other organically.
- Scroll reveal: class .reveal on sections, JS IntersectionObserver adds .visible with opacity 0→1 + translateY(24px→0), transition 0.6s ease

---

## SECTION STRUCTURE (mandatory order)

### 1. FIXED HEADER (sticky top)

- Background #000, height 64px, z-index 1000
- Logo left: "SuaProteção" in #1C9C4B bold + "Veicular" in #FFFFFF (Montserrat 900)
- Button right: "Quero Proteger Meu Carro →" (green #1C9C4B, color #FFFFFF, border-radius 6px, anchor link to #formulario)
- On scroll past 80px: add box-shadow 0 2px 20px rgba(28,156,75,0.3) via JS

### 2. HERO (100vh)

- Background: diagonal green-to-black gradient (from #000000 to #0d1f12)
- H1: "Proteção Veicular a partir de R$ 2,46/dia" — Montserrat 900, fluid size via clamp(), green shimmer gradient via background-clip text
- H2/subtitle: "Melhor que seguro, sem burocracia. Sem análise de perfil, sem franquia absurda." — color #EEEEEE, 1.3rem
- Support paragraph: "Associação de proteção veicular: você paga apenas a adesão + mensalidade. Cancele quando quiser." — color #888888
- Primary CTA: large button "Quero Minha Proteção Agora" (green gradient, color #FFFFFF, anchor link to #formulario)
- Badge below button: "✅ Sem análise de crédito ✅ 100% online ✅ Assistência 24h" — color #EEEEEE, font-size 0.9rem
- Image/SVG: inline SVG stylized car (right side on desktop, below on mobile) with silhouette in green tones on dark background
- Layout: CSS Grid 2 columns desktop, 1 column mobile

### 3. BENEFITS SECTION

- Section title: "Tudo que você precisa em um único plano" — H2 white centered
- Subtitle: "Cobertura completa, mensalidade justa, suporte real." — color #888888
- Grid 3x2 desktop / 1 column mobile (CSS Grid)
- 6 cards: background #0f1a13, border 1px solid rgba(28,156,75,0.15), border-radius 12px, padding 24px
- Hover: border-color #1C9C4B, transform translateY(-4px), box-shadow 0 0 24px rgba(28,156,75,0.2), transition 0.3s
- Each card: inline SVG icon (60x60, color #1C9C4B) + bold white title + #888888 description

CARDS (exact content in pt-BR):

1. 🔒 **Roubo e Furto** — "Os índices de roubo não param de crescer. Seu carro protegido contra subtração total."
2. 🚗 **Colisão** — "Acidentes podem custar uma fortuna. Com a SuaProteção, você não arca sozinho."
3. 🚑 **Assistência 24h** — "Suporte a qualquer hora, em qualquer lugar. Pane, acidente ou emergência."
4. 📡 **Rastreamento** — "Controle total da localização do seu veículo pelo celular, com opção de bloqueio remoto."
5. 🚛 **Reboque até 1.000 km** — "Se seu veículo parar, acionamos reboque sem custo extra — até 1.000 km de cobertura."
6. 🌧️ **Fenômenos Naturais** — "Granizo, enchente, queda de árvore? Protegido contra tudo que a natureza pode causar."

### 4. COMPARISON SECTION

- Background #0a0f0c, padding 80px 0
- Title: "Por que escolher proteção veicular?" — H2 white centered
- Comparison table 3 columns: | Critério | Seguro Tradicional | SuaProteção |
- Table rows:
  - Análise de perfil | ❌ Sim | ✅ Não
  - Franquia alta | ❌ Sim | ✅ Não
  - Burocracia | ❌ Muita | ✅ Zero
  - Cancelamento livre | ❌ Multa | ✅ Livre
  - Assistência 24h | ❌ Limitada | ✅ Completa
  - Preço | ❌ Caro | ✅ A partir de R$2,46/dia
- Table style: background #0f1a13, header row background #1C9C4B bold text #FFFFFF, alternating rows #0a0f0c/#0f1a13, text #EEEEEE
- SuaProteção column values: color #1C9C4B, font-weight 700

### 5. TESTIMONIALS

- Title: "O que nossos associados dizem" — H2 white centered
- 3 cards in pure JS slider (green prev/next buttons, dot indicators, 5s autoplay)
- Each card: background #0f1a13, border 1px solid rgba(28,156,75,0.15), left accent border 4px solid #1C9C4B, italic #EEEEEE quote, name + city in #1C9C4B, stars ⭐⭐⭐⭐⭐
- Glassmorphism: backdrop-filter blur(12px), background rgba(255,255,255,0.02)

TESTIMONIALS (pt-BR):

1. "Já tive carro roubado antes sem proteção. Agora durmo tranquilo. O processo foi rápido e sem dor de cabeça." — _Carlos M., São Paulo/SP_
2. "Paguei mais barato que qualquer seguro e a cobertura é completa. Indico pra todo mundo." — _Fernanda R., Goiânia/GO_
3. "Bati o carro numa sexta à noite. Na segunda já tinham me dado retorno. Atendimento excelente!" — _Ricardo T., Belo Horizonte/MG_

### 6. FAQ (accordion)

- Title: "Dúvidas frequentes" — H2 white centered
- 4 questions with JS toggle (animated max-height, no libs)
- Question bar: background #0f1a13, border 1px solid rgba(28,156,75,0.15), color #FFFFFF, hover border-color #1C9C4B
- "+" icon color #1C9C4B, becomes "−" when open
- Answer text: color #888888, padding 16px 24px

QUESTIONS (pt-BR):

1. **É um seguro?** → "Não. Somos uma Associação de Proteção Veicular — sociedade civil sem fins lucrativos. Você contribui mensalmente junto a outros associados para cobertura coletiva. Sem SUSEP, sem burocracia de seguradora."
2. **Tem análise de perfil ou crédito?** → "Não. Ao contrário dos seguros tradicionais, não analisamos perfil socioeconômico, local de moradia ou histórico de sinistros. Todos são bem-vindos."
3. **Como funciona o pagamento?** → "Você paga uma taxa de adesão única e as mensalidades mês a mês via boleto ou PIX. Pode cancelar a qualquer momento, sem multa."
4. **Como aciono a proteção?** → "Pelo nosso WhatsApp ou central 24h. O atendimento é rápido, direto e sem papelada excessiva."

### 7. MAIN FORM

- ID: `formulario`
- Background: dark gradient #0a0f0c → #0f1a13
- Title: "Garanta sua proteção agora" — H2 white
- Subtitle: "Preencha e entraremos em contato em até 2 horas úteis." — color #888888
- Fields (all labels in pt-BR):
  - Labels: color #EEEEEE, font-family Montserrat, font-weight 700
  - Inputs: background #152b1c, border 1px solid rgba(28,156,75,0.25), color #EEEEEE, border-radius 8px
  - Input focus: border-color #1C9C4B, box-shadow 0 0 0 3px rgba(28,156,75,0.15)
  - Nome completo (required, minlength 3)
  - E-mail (required, type email)
  - Telefone/WhatsApp (required, JS mask: (00) 00000-0000)
  - Cidade (required)
  - Select "Tipo de veículo": Carro de Passeio / Caminhonete / Moto / Caminhão / Outro
- Submit button: "Quero Minha Proteção →" (green gradient, color #FFFFFF, full width, font-size 1.2rem)
- JS validation before submit: required fields + email format + phone min 14 chars
- onSubmit: preventDefault → fetch POST to:
  `https://api.avizzap.com/v1/webhook/1ee3a5a3-4c04-4029-ba36-379ab0dece7b`
  headers: { "Content-Type": "application/json" }
  body: JSON.stringify({ nome, email, telefone, cidade, veiculo })
- Success: overlay background rgba(28,156,75,0.95) with message "✅ Recebemos seu contato! Em breve nossa equipe entrará em contato pelo WhatsApp." + close button
- Error: inline red message "Erro ao enviar. Tente novamente."

### 8. FOOTER

- Background #000000, padding 48px 0
- Logo: "SuaProteção" in #1C9C4B + "Veicular" in #FFFFFF
- Tagline: color #888888
- WhatsApp SVG icon (#1C9C4B) + "(62) 99999-9999" in #EEEEEE
- Instagram icon (#1C9C4B) + "@suaprotecaoveicular" in #EEEEEE
- "© 2026 SuaProteção Veicular. Todos os direitos reservados." — color #888888
- Disclaimer: "Associação de Proteção Veicular. Não é seguro. Não é regulada pela SUSEP." — color #555555, font-size 0.8rem
- All centered, links color #1C9C4B on hover

---

## FLOATING WHATSAPP BUTTON

- Fixed bottom-right corner
- 60px circle, background #1C9C4B, white SVG WhatsApp icon
- Link: `https://wa.me/5562999999999?text=Quero+saber+sobre+proteção+veicular`
- Pulsing CSS keyframe animation using rgba(28,156,75,0.4)

---

## REQUIRED JS (no external libraries)

1. Sticky header shadow on scroll
2. Phone input mask (real-time character replacement)
3. Form validation with inline error messages in pt-BR
4. Async POST fetch with success/error overlay
5. Testimonials slider (prev/next + 5s autoplay + dots)
6. FAQ accordion with max-height animation
7. Scroll reveal via IntersectionObserver: .reveal → .visible (opacity 0→1, translateY 24px→0, transition 0.6s ease)

---

## SEO & META TAGS

```html
<title>Proteção Veicular Barata - SuaProteção Veicular</title>
<meta
  name="description"
  content="Proteção veicular a partir de R$2,46/dia. Sem análise de perfil, sem franquia abusiva. Roubo, colisão, assistência 24h, rastreamento e reboque 1000km."
/>
<meta
  property="og:title"
  content="SuaProteção Veicular — A partir de R$2,46/dia"
/>
<meta
  property="og:description"
  content="Melhor que seguro, sem burocracia. Proteja seu veículo agora."
/>
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

---

## GENERAL RULES

- Pure CSS: flexbox + grid, zero Bootstrap, zero jQuery, zero external libraries
- Mobile-first: main breakpoint at 768px
- Smooth interactions: transition 0.3s ease on all interactive elements
- Scroll behavior: smooth on html element
- Section dividers: full-width inline SVG wave shape between sections, path fill color matches next section's background, alternate direction with transform: scaleX(-1) for visual rhythm
- ALL page content (headings, body text, buttons, labels, testimonials, FAQ, form fields, success/error messages, footer) MUST be written in Brazilian Portuguese (pt-BR)
- Only code, variable names and HTML comments should be in English
- Output: ONLY the raw HTML. No explanations, no markdown, no code blocks. Just raw HTML ready to save as index.html and open in a browser.
