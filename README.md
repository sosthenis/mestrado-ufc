# 🎓 Portal Acadêmico PPAC — UFC/FEAAC

**Mestrado Profissional em Administração e Controladoria (PPAC PROF)**  
Turma COGERH 2026.1 · Universidade Federal do Ceará

---

## 📋 Visão Geral

Portal web acadêmico desenvolvido em HTML, CSS e JavaScript puro para acompanhamento das disciplinas, materiais de aula e progresso do curso de Mestrado Profissional em Administração e Controladoria (PPAC PROF) da UFC — Turma COGERH 2026.1.

O portal funciona como um **dashboard pessoal do mestrando**, integrando acesso a materiais hospedados no Firebase Storage, acompanhamento de progresso acadêmico e um assistente de IA contextualizado ao programa.

---

## 🌐 Tecnologias Utilizadas

| Tecnologia | Uso |
|---|---|
| **HTML5** | Estrutura semântica da aplicação |
| **CSS3 Vanilla** | Estilização, glassmorphism, animações |
| **JavaScript (ES6+)** | Lógica, integrações e renderização dinâmica |
| **Firebase Storage** | Armazenamento e entrega dos materiais em PDF/DOCX |
| **Gemini API** | Motor primário do assistente de IA (gratuito) |
| **OpenAI API** | Motor secundário do assistente de IA (GPT-4o Mini) |
| **Google Fonts** | Tipografia: Inter + Outfit |
| **Font Awesome 6** | Ícones de interface |

---

## ✨ Funcionalidades

### 1. 🏠 Hero Section — Cabeçalho Animado
- Tema dark navy com **glassmorphism** premium
- **3 fitas SVG animadas** com gradientes (Wave Glass aesthetic)
- **Ondas paralaxe** na base da seção (efeito de profundidade)
- **Efeitos de brilho** (glows) pulsantes nas bordas
- **Shimmer animado** percorrendo o hero
- **Cards de estatísticas** com hover e transições suaves:
  - Disciplinas ativas
  - Carga Horária integralizada (%)
  - Créditos exigidos (30)
  - Prazo final (FEV/2028)

---

### 2. 🔵 Barra de Status Firebase
- Aparece no topo ao carregar a página
- Verifica conectividade com o Firebase Storage
- Estados: `checking` (âmbar) → `connected` (verde) → `error` (vermelho)
- Some automaticamente após 6 segundos quando conectado

---

### 3. 🧭 Navegação Glass
- **Navbar sticky** com blur e saturate (glassmorphism)
- Links: Perfil | Progresso | Disciplinas | NotebookLM
- **Botão NotebookLM** com gradiente animado (cores Google)
- **Menu hambúrguer** responsivo para dispositivos móveis (com animação de transformação X)
- Menu mobile dropdown com efeito blur

---

### 4. 👨‍🎓 Perfil do Aluno
- Card com grade de informações acadêmicas:
  - Status (ATIVO — badge com ponto verde piscante)
  - Tempo de curso / Mês atual
  - Programa PPAC
  - Ciclo e prazo final
  - Matriz curricular
  - Área de atuação
  - Linha estratégica
  - Via de ingresso
  - Orientação
  - Instituição
  - Link para SIGAA UFC
  - Link para NotebookLM

---

### 5. 📊 Progresso Acadêmico

#### Barras de Progresso
- **Carga Horária**: X / 480 horas (animação suave com cubic-bezier)
- **Créditos**: X / 30 créditos
- Cores distintas: azul (CH) e dourado (créditos)

#### Linha do Tempo
- 6 marcos sequenciais com dots coloridos:
  1. ✅ Ingresso — MAR/2026
  2. 🔵 Disciplinas — 2026 (atual)
  3. ⭕ Proficiência — 2026
  4. ⭕ Qualificação — 2027
  5. ⭕ Dissertação — 2027/28
  6. ⭕ Defesa — FEV/2028

---

### 6. 📚 Disciplinas

#### Sistema de Abas
- **Todas** — exibe todas as 6 disciplinas
- **Matriculadas** — filtra disciplinas com status `matriculado`
- **Pendentes** — exibe componentes pendentes em cards menores

#### Cards de Disciplina
Cada card exibe:
- Ícone colorido por disciplina
- Badge de status (Matriculado / Pendente / Concluído)
- Nome e código
- Carga horária, créditos, número de aulas e arquivos
- Prévia da ementa
- Botão "Ver Materiais e Aulas"

#### Disciplinas Cadastradas

| Código | Disciplina | CH | Créditos | Status |
|---|---|---|---|---|
| EDP704A | Teoria das Organizações | 48h | 3 | Matriculado |
| EDP705A | Metodologia de Pesquisa | 48h | 3 | Matriculado |
| EHP713A | Controladoria | 48h | 3 | Matriculado |
| EHP0108 | Proficiência | 16h | 0 | Pendente |
| EHP0049 | Qualificação | 16h | 0 | Pendente |
| EDP799A | Dissertação | 96h | 0 | Pendente |

---

### 7. 🗂️ Painel de Detalhes da Disciplina
- Abre em overlay full-screen com animação (`slideIn`)
- Exibe: status, carga horária, créditos, total de arquivos
- **Ementa completa** da disciplina
- Lista de aulas com **accordions expansíveis**
  - Cada aula mostra: número, título, contagem de arquivos
  - Arquivos com ícone por tipo (PDF: vermelho, DOCX: azul)
  - Badge de extensão
  - Botão de abertura/download via Firebase Storage
  - Arquivos sem link exibidos com aviso ⚠️
- Fecha com botão ✕ ou tecla `Escape`

---

### 8. 🤖 Assistente de IA Acadêmico

#### Avatar FAB (Floating Action Button)
- Foto do perfil circular flutuante (`bot-avatar.png`)
- Fallback SVG desenhado: avatar masculino com óculos e livro
- Animação `fabFloat` (sobe/desce suavemente)
- Anéis pulsantes (`ringPulse`) em azul e verde
- Badge de status online (ponto verde piscante)
- Posicionado no canto inferior direito

#### Painel do Chat (420px, glassmorphism)
- **2 abas de modo**:
  - ⚙️ **Via API** — integração direta com a IA (requer API key)
  - 🔗 **Acesso Direto** — abre o chat no site oficial sem key

##### Modo Via API
- **Seletor de motor de IA**:
  - 🟢 **Gemini** (gratuito) — padrão recomendado
  - ⚡ **GPT-4o Mini** (OpenAI) — pago
- Histórico de conversa com rolagem automática
- Indicador de digitação animado (3 pontos bouncing)
- Mensagens do bot (bolhas azuis à esquerda) e usuário (bolhas à direita)
- Mensagens de erro em vermelho com ícone de alerta
- **Formulário inline para API Key** (salva no localStorage)
- Indicador de status da key (verde = ativa, âmbar = ausente)

##### Fallback Automático Gemini
Sistema de fallback automático entre modelos Gemini quando a cota esgota:
1. `gemini-2.0-flash` (tentativa 1)
2. `gemini-1.5-flash` (tentativa 2)
3. `gemini-1.5-flash-8b` (tentativa 3)
- Persiste o modelo funcional no localStorage
- Notifica o usuário quando muda de modelo

##### Modo Acesso Direto
- Botão **Assistente PPAC (ChatGPT)** — abre GPT customizado do programa
- Botão **Gemini (Google)** — abre Gemini com prompt contextualizado ao PPAC
- Botão **NotebookLM** — para pesquisa com documentos próprios
- Prompt PPAC pré-preenchido com contexto das disciplinas

#### Sistema Prompt do Assistente
Contexto especializado em:
- Teoria das Organizações (Taylor, Fayol, Weber, Foucault, Braverman)
- Metodologia de Pesquisa (qualitativa, quantitativa, ABNT, projetos)
- Controladoria (BSC, orçamento, custos, gestão de desempenho)
- Respostas sempre em português brasileiro com linguagem acadêmica
- Auxílio para fichamentos, resenhas e sínteses

---

### 9. ☁️ Integração Firebase Storage
- Materiais hospedados em `mestrado-ppac.firebasestorage.app`
- Arquivos acessados via URL autenticada (token de acesso)
- Verificação de conectividade no carregamento da página
- Fallback para dados locais (BACKUP_DATA) quando offline

---

## 📁 Estrutura de Arquivos

```
MESTRADO UFC 2/
├── index.html              # Aplicação principal (único arquivo ~90KB)
├── index2.html             # Versão alternativa/backup
├── bot-avatar.png          # Avatar circular do assistente IA
├── backup_ppac_11-04-2026.json  # Backup dos dados locais
├── bot ppac/               # Pasta da landing page do bot
│   ├── index.html
│   ├── style.css
│   └── script.js
├── Controladoria/          # Materiais da disciplina
├── Controladoria & Metodologia de Pesquisa/
├── Teoria das organizações/
├── MESTRADO UFC 1/         # Arquivos da fase anterior
└── pasta sem título/
```

---

## 🎨 Design System

### Paleta de Cores

| Token | Hex | Uso |
|---|---|---|
| `--navy` | `#0b1623` | Background principal |
| `--navy2` | `#101d2e` | Superfícies secundárias |
| `--navy3` | `#162640` | Superfícies terciárias |
| `--blue` | `#0e6ba8` | Azul primário |
| `--blue2` | `#1a8cdb` | Azul hover |
| `--blue3` | `#4fc3f7` | Azul accent/links |
| `--gold` | `#c9962a` | Dourado primário |
| `--gold2` | `#e8b444` | Dourado hover |
| `--green` | `#10B981` | Sucesso / ativo |
| `--red` | `#EF4444` | Erro / alerta |
| `--amber` | `#F59E0B` | Aviso / pendente |
| `--purple` | `#8B5CF6` | Proficiência |

### Tipografia
- **Outfit** — Títulos e displays (Bold 700/800)
- **Inter** — Corpo de texto e UI (300/400/500/600/700)

### Componentes Visuais
- **Glassmorphism**: `backdrop-filter: blur(20px) saturate(1.3)`
- **Bordas**: `rgba(255,255,255,0.08)` para sutileza
- **Sombras**: `0 12px 40px rgba(0,0,0,0.4)`
- **Border-radius**: 15px (cards) / 10px (elementos menores)
- **Transições**: `cubic-bezier(.4,0,.2,1)` para suavidade premium

---

## ⌨️ Atalhos de Teclado

| Tecla | Ação |
|---|---|
| `Escape` | Fecha painel de disciplina ou chat |
| `Enter` (no chat) | Envia mensagem |

---

## 🔗 Links Externos Integrados

- [SIGAA UFC](http://si3.ufc.br/sigaa) — Portal acadêmico da universidade
- [NotebookLM](https://notebooklm.google.com/) — Pesquisa com documentos
- [Google AI Studio](https://aistudio.google.com/apikey) — Obtenção de API key Gemini
- [OpenAI Platform](https://platform.openai.com/api-keys) — API key GPT
- [Assistente PPAC (ChatGPT)](https://chatgpt.com/g/g-p-69d7197f09d48191bf754d9dfc32ee9e-assistente-ppac/project) — GPT customizado para o programa

---

## 📱 Responsividade

| Breakpoint | Adaptações |
|---|---|
| `> 768px` | Layout completo, navegação desktop com todos os links |
| `≤ 768px` | Menu hambúrguer, cards em coluna única, chat redimensionado |
| `≤ 480px` | Card do aluno em coluna única |

---

## 🗓️ Linha do Tempo do Programa

```
MAR/2026         2026            2026           2027          2027/28        FEV/2028
   │               │               │               │               │               │
[✅ Ingresso] → [🔵 Disc.] → [Profic.] → [Qualif.] → [Dissert.] → [Defesa]
```

---

## 👨‍🎓 Dados do Aluno

| Campo | Valor |
|---|---|
| **Status** | ATIVO |
| **Programa** | Mestrado em Administração e Controladoria (Profissional) |
| **Instituição** | UFC / FEAAC — Fortaleza, CE |
| **Inicio** | MAR/2026 |
| **Prazo Final** | FEV/2028 |
| **Currículo** | 2022.1 |
| **Área** | Gestão Organizacional |
| **Linha** | Estratégias e Sustentabilidade |
| **Total de Créditos Exigidos** | 30 créditos |
| **Carga Horária Total** | 480 horas |

---

## 📌 Observações Técnicas

- **Sem dependências externas de build** — o projeto é um único `index.html` auto-contido
- **API keys armazenadas no `localStorage`** do navegador (nunca enviadas ao servidor)
- **Dados de disciplinas** embutidos como `BACKUP_DATA` no JS, com possibilidade de atualização via Firebase
- **Histórico de chat** mantido em memória (session-based, não persistido)
- **Modelo Gemini** com persistência do índice do modelo funcional no localStorage

---

*Portal PPAC UFC · Turma COGERH 2026.1 · Desenvolvido com HTML, CSS e JS puro*
