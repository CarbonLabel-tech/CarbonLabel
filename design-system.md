# CarbonLabel Design System

Este documento define os padrões visuais, tokens de design e componentes da interface CarbonLabel. Deve ser utilizado como referência única para a criação de novas páginas e aplicações, garantindo consistência visual e arquitetural.

## 1. Visão Geral (Brand Identity)

A identidade visual da CarbonLabel combina **minimalismo corporativo** com **estética técnica/industrial (Data/Infra)**.
*   **Keywords**: Engenharia, Precisão, Infraestrutura, "Ground Truth", Transparência.
*   **Estilo**: Clean, uso extensivo de espaços em branco, tipografia monoespaçada para dados/meta-informação e grids geométricos de fundo.

## 2. Design Tokens

### 2.1 Cores

| Token | Valor (Tailwind) | Hex | Uso Principal |
| :--- | :--- | :--- | :--- |
| **Primary / Surface** | `slate-900` | `#0f172a` | Headers, Botões Primários, Seções Dark, Footer Logo BG |
| **Background Main** | `white` | `#ffffff` | Fundo principal da página, Cards |
| **Background Alt** | `slate-50` | `#f8fafc` | Seções secundárias, Fundo de cards em hover |
| **Text Primary** | `slate-900` | `#0f172a` | Títulos principais |
| **Text Body** | `slate-600` | `#475569` | Texto corrido, descrições |
| **Text Muted** | `slate-500` | `#64748b` | Legendas, meta-dados, links de footer |
| **Text Tech/Subtle**| `slate-400` | `#94a3b8` | Labels técnicos, bordas de ícones, separadores |
| **Accent Blue** | `blue-900` / `blue-500` | Variado | Sombras de botões, highlights em hover, links ativos |
| **Accent Green** | `green-500` / `green-400`| Variado | Status "Online", Indicadores de sucesso, "Processing" |
| **Borders** | `slate-200` | `#e2e8f0` | Divisórias sutis, bordas de cards padrão |
| **Borders Dark** | `slate-800` | `#1e293b` | Bordas em superfícies escuras |

### 2.2 Tipografia

Utiliza-se uma combinação de **Sans-serif** para legibilidade e **Monospace** para estética técnica.

*   **Font Family Main**: `font-sans` (Padrão do sistema/Tailwind).
*   **Font Family Tech**: `font-mono` (Padrão do sistema/Tailwind). Usado em: Menus, Botões, Meta-dados (`v2.4.0`), Títulos de Cards.

**Hierarquia:**

*   **Display (Hero)**: `text-4xl` a `7xl`, `font-extrabold`, `tracking-tight`, `font-mono`. Leading `[1.1]`.
*   **Section Heading**: `text-3xl` a `4xl`, `font-bold`, `tracking-tight`, `font-mono`.
*   **Card Title**: `text-lg` a `xl`, `font-bold`, `font-mono`, `tracking-tight`.
*   **Body**: `text-base` a `lg`, `leading-relaxed`, `text-slate-600`.
*   **Small/Meta**: `text-xs` ou `text-[10px]`, `uppercase`, `tracking-wide`, `font-mono`, `text-slate-400/500`.

### 2.3 Espaçamentos & Layout

*   **Container**: `max-w-7xl mx-auto px-4 md:px-6`.
*   **Section Padding**: `py-16` (64px) a `py-24` (96px) em Desktop.
*   **Element Gaps**: Padrões de `gap-4` (16px), `gap-6` (24px), `gap-8` (32px).
*   **Radius**:
    *   Geral: `rounded-lg` (Botões, Cards, Inputs).
    *   Pequeno: `rounded` (Ícones containers, badges).

### 2.4 Efeitos & Decoração

*   **Sombras**: Suaves e coloridas. Ex: `shadow-lg shadow-blue-900/20`.
*   **Bordas Decorativas**:
    *   `border-dashed`: Linhas de conexão, divisórias internas de cards.
    *   `Tech Corners`: Quadrados absolutos nos cantos de cards (`w-2 h-2 border-l-2 border-t-2`) que mudam de cor no hover.
*   **Fundos**:
    *   Grid Patterns: `bg-[size:3rem_3rem]` com gradientes lineares.
    *   Backdrop Blur: `backdrop-blur-md` na navegação sticky e overlays.

---

## 3. Componentes

### 3.1 Buttons

**Primary Button**
*   **Classes**: `bg-[#0f172a] text-white font-bold font-mono tracking-tight rounded-lg shadow-lg shadow-blue-900/20 border border-slate-800`.
*   **Hover**: `hover:bg-[#1e293b] hover:-translate-y-0.5`.
*   **Decoração**: Efeito interno de "cruz de mira" ou linhas técnicas no hover (opcional).

**Secondary Button**
*   **Classes**: `bg-white border-2 border-slate-200 text-slate-700 font-bold font-mono tracking-tight rounded-lg`.
*   **Hover**: `hover:border-[#0f172a] hover:text-[#0f172a]`.

### 3.2 Cards (Service/Feature)

*   **Container**: `bg-white border border-slate-200 p-6 md:p-8 rounded-lg overflow-hidden relative group`.
*   **Hover Behavior**: `hover:shadow-xl hover:shadow-blue-900/5 hover:border-blue-400/50 hover:-translate-y-1 transition-all`.
*   **Ícone**: Dentro de um container quadrado: `w-12 h-12 bg-slate-50 border border-slate-100 rounded-md`. Fica escuro (`#0f172a`) no hover.
*   **Conteúdo Extra**: Lista de features separada por linha tracejada (`border-t border-slate-100 border-dashed`).

### 3.3 Badges & Status

*   **Status Online/System**: `bg-white border border-blue-200 text-blue-900 font-mono text-xs font-bold px-4 py-1.5 rounded shadow-sm`. Com "dot" verde pulsante.
*   **Tech Labels**: `text-[10px] font-mono text-slate-400 uppercase`. Ex: `module: core_services`.

### 3.4 Inputs (Forms)

*   **Style**: `bg-slate-900 border border-slate-700 text-white rounded px-4 py-3 font-mono text-sm`.
*   **Focus**: `focus:border-green-500 focus:outline-none`.
*   **Placeholder**: `text-slate-500`.
*   *Nota*: Usado principalmente em fundos escuros (Seção de Contato). Para fundos claros, inverter as cores (bg-white, border-slate-200, text-slate-900).

### 3.5 Navigation Bar

*   **Comportamento**: Sticky. Transparente (`bg-white/50`) no topo, Sólida/Blur (`bg-white/95 backdrop-blur-md`) ao rolar.
*   **Links**: `text-sm font-bold text-slate-600 uppercase tracking-wide font-mono`.
*   **Logo**: Ícone em box escuro (`bg-[#0f172a]`) + Texto "CarbonLabel" (`font-light` + `font-normal`).

---

## 4. Estrutura de Layout (Wireframe)

Ao criar novas páginas, siga esta estrutura:

1.  **Navbar Fixa**: Sempre presente.
2.  **Backbone (Opcional)**: Linha vertical tracejada no centro ou esquerda (`w-px bg-slate-200 border-l border-dashed`) percorrendo a altura da página para dar sensação de "conectividade".
3.  **Hero Section**:
    *   Padding generoso no topo (`pt-28` min).
    *   Título grande monoespaçado.
    *   Badge de "Status" ou "Contexto" acima do título.
    *   Fundo com Grid sutil.
4.  **Content Sections**:
    *   Alternar entre fundo Branco e `slate-50`.
    *   Usar divisores de borda `border-t border-slate-200`.
    *   Títulos de seção acompanhados de ícone ou label técnico.
5.  **CTA Final**: Fundo escuro (`#0f172a`), elementos "tech" (grids, linhas verdes), formulário ou botão de ação direta.
6.  **Footer**: Simples, clean, links em colunas ou linha, copyright monoespaçado.

## 5. Regras de Implementação

1.  **Use `lucide-react`** para ícones. Espessura de traço (`strokeWidth`) geralmente `1.5` para elegância.
2.  **Animações**: Use `framer-motion` para entradas suaves (`FadeIn` com `y: 10` -> `y: 0`).
3.  **Responsividade**:
    *   Padrão Mobile First.
    *   Fontes grandes no desktop, ajustadas para mobile.
    *   Cards viram lista vertical em mobile.
    *   Menu vira Hamburger em mobile.
4.  **Decoração Técnica**: Não deixe a UI "chapada". Adicione pequenos detalhes como:
    *   `border-dashed`.
    *   Dots/Squares decorativos absolutos.
    *   Labels de "versão" ou "módulo" (`v2.4.0`) em cantos.

---
*Documento gerado automaticamente a partir da análise de `homepage.html`.*
