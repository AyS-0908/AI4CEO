# Design System — AI4CEO

Référence de design pour le prototype single-file `index.html`.
Inspiré de [fr.ippon.tech](https://fr.ippon.tech) : professionnel, moderne, sobre.

---

## Tokens de design (`:root`)

### Fonds

| Token | Valeur | Usage |
|-------|--------|-------|
| `--bg` | `#0a0c12` | Fond de page principal |
| `--surface` | `#13161f` | Sections alt (`.section-alt`), nav mobile, footer |
| `--surface-2` | `#1c2030` | Cards, inputs, panels élevés |
| `--border` | `#252836` | Bordures générales, séparateurs |
| `--border-sub` | `#1e2130` | Dividers internes très subtils (ex. ombre du header) |

### Accent

| Token | Valeur | Usage |
|-------|--------|-------|
| `--accent` | `#4070ff` | Bouton primaire, bullets, labels, highlights |
| `--accent-h` | `#2f5fe8` | Hover du bouton primaire |
| `--accent-dim` | `rgba(64,112,255,0.12)` | Fond teinté accent (quote, step-num glow, focus ring) |

### Texte

| Token | Valeur | Usage |
|-------|--------|-------|
| `--text` | `#eef0f6` | Texte principal, titres, `<strong>` |
| `--muted` | `#7a7f9a` | Corps de texte secondaire, labels |
| `--muted-2` | `#5a5f7a` | Placeholders, metadata, texte tertiaire |

### Typographie

| Token | Valeur | Usage |
|-------|--------|-------|
| `--font` | system-ui stack | Corps du texte |
| `--font-mono` | `'SF Mono','Fira Code','Consolas',monospace` | Code, badges prototype |
| `--text-xs` | `0.75rem` | Labels très petits, badges |
| `--text-sm` | `0.875rem` | Texte secondaire, meta |
| `--text-base` | `1rem` | Corps standard |
| `--text-lg` | `1.125rem` | Corps dans les cards |

### Espacement

| Token | Valeur | Usage |
|-------|--------|-------|
| `--space-xs` | `0.5rem` | Micro-gaps |
| `--space-sm` | `0.75rem` | Padding boutons (vertical) |
| `--space-md` | `1.25rem` | Gaps internes |
| `--space-lg` | `2rem` | Padding boutons (horizontal), gaps |
| `--space-xl` | `3.5rem` | Espacements larges |
| `--space-2xl` | `5rem` | Padding sections (`.section`) |

### Forme et animation

| Token | Valeur | Usage |
|-------|--------|-------|
| `--radius` | `6px` | Boutons, inputs, badges |
| `--radius-lg` | `12px` | Cards, panels, illustrations |
| `--ease` | `cubic-bezier(0.16,1,0.3,1)` | Transitions spring (hover cards) |
| `--dur-fast` | `0.15s` | Transitions boutons |
| `--dur-base` | `0.22s` | Transitions cards/hover |

### Ombres

| Token | Valeur | Usage |
|-------|--------|-------|
| `--shadow-card` | `0 1px 3px rgba(0,0,0,0.4), 0 0 0 1px var(--border)` | Cards au repos |
| `--shadow-elevated` | `0 4px 16px rgba(0,0,0,0.5), 0 0 0 1px var(--border)` | Cards au hover, modals |

---

## Inventaire des composants CSS

### Layout

| Classe | Description |
|--------|-------------|
| `.container` | Centrage max-width 960px, padding horizontal 1.5rem |
| `.site-main` | Padding-top = `--nav-h` pour compenser le header fixe |
| `.page` | Section de page (masquée) — `.page.active` affiche |
| `.section` | Espacement vertical `--space-2xl` |
| `.section-alt` | Fond `--surface` |
| `.section-center` | Alignement centré |
| `.sr-only` | Accessibilité — visuellement masqué |

### Navigation

| Classe | Description |
|--------|-------------|
| `.site-header` | Header fixe, `height: --nav-h`, backdrop blur |
| `.nav-inner` | Flex row — logo + links + hamburger |
| `.nav-logo` | Logo "AI4CEO" (AI en accent) |
| `.nav-links` | Navigation horizontale desktop |
| `.nav-hamburger` | Bouton 3 barres mobile |
| `.nav-mobile` | Menu mobile vertical (`.open` = visible) |

### Typographie

| Classe | Description |
|--------|-------------|
| `.section-label` | Étiquette de section — uppercase, accent, `letter-spacing: 0.09em` |
| `.section-title` | `margin-bottom: 1rem` |
| `.section-lead` | Corps élargi, max-width 640px |
| `.hero-eyebrow` | Identique à `.section-label` — utilisé dans le hero |

### Boutons

| Classe | Description |
|--------|-------------|
| `.btn-primary` | Fond accent, blanc, focus-visible ring |
| `.btn-ghost` | Transparent, bordure, focus-visible ring |
| `.btn-sub` | Sous-texte interne au bouton — `display:block`, xs, opacité 70% |

### Cards

| Classe | Description |
|--------|-------------|
| `.card` | Card usage-case — `surface-2`, `radius-lg`, `shadow-card`, hover lift |
| `.card-grid` | Grille auto-fill min 270px |
| `.card-num` | Numéro 01–06, xs, accent |
| `.value-item` | Item ROI — même traitement que `.card` |
| `.value-bullet` | Bullet accent 8×8px |
| `.testi-card` | Card témoignage — `surface-2`, `radius-lg`, `shadow-card` |
| `.testi-thumb` | Zone image/vidéo 155px — fond `surface` |
| `.testi-play` | Bouton play rond accent |
| `.testi-info` | Zone texte sous l'image |
| `.testi-label` | Badge "Témoignage à venir" |
| `.note-card` | Note réflexion — `surface-2`, border-left accent, `radius-lg`, `shadow-card` |

### Formulaire

| Classe | Description |
|--------|-------------|
| `.form-page` | Conteneur max-width 560px centré |
| `.form-group` | Groupe label + input |
| `.form-label` | Label champ |
| `.form-input` / `.form-select` | Inputs — fond `surface-2`, focus: border accent |
| `.form-submit` | Bouton pleine largeur |
| `.form-success` | Message succès (`.visible` = affiché) |

### Parcours (Écran 5)

| Classe | Description |
|--------|-------------|
| `.step-list` | Liste verticale avec ligne de connexion |
| `.step-num` | Cercle numéroté — `surface-2`, glow `accent-dim` |
| `.step-body` | Contenu de l'étape |
| `.quote` | Citation — fond `accent-dim`, border-left accent |

### Footer & utilitaires

| Classe | Description |
|--------|-------------|
| `.site-footer` | Fond `surface`, border-top |
| `.prototype-badge` | Badge "0 donnée stockée" — `font-mono` |
| `.placeholder-hero` | Héro pleine hauteur pour pages secondaires |
| `.illus-placeholder` | Placeholder illustration — dashed border, aspect-ratio 4/3 |

### Kit IA-PDG (Page 4 — seams d'intégration)

| Classe | Description |
|--------|-------------|
| `.tools-grid` | Colonne d'outils |
| `.tool-section` | Un outil — header + body |
| `.tool-header` | En-tête numéroté |
| `.tool-body` | Corps — point d'intégration externe |
| `.tool-placeholder` | Texte "prochainement" temporaire |

---

## Convention SVG (Phases 2–4)

Pour toutes les illustrations inline — pas d'asset externe, pas d'image.

| Paramètre | Valeur |
|-----------|--------|
| Stroke | `var(--accent)` (éléments principaux) ou `var(--muted)` (secondaires) |
| Fill figures | `none` ou `var(--accent-dim)` (très léger) |
| Fill fonds de panels | `var(--surface-2)` |
| Taille max | viewBox ≤ `400×280` (portrait/paysage selon contexte) |
| Hub diagram | viewBox `360×360` |
| Wrapper | `.illus-wrap` — max-width 420px, margin auto |
| Fallback | `.illus-placeholder` si SVG insatisfaisant visuellement |

---

## Règles éditoriales

- Audience : PDGs francophones, entreprises 100+ personnes, IA-curieux non-techniques
- Ton : PDG-to-PDG, sobre, direct, crédible — jamais "marketing agressif"
- Éviter : "révolutionnaire", "disruptif", "game changer", buzzwords, anglicismes, jargon technique
- Préférer : concret, usage, recul, responsabilité, arbitrage, sérénité, leadership
- Densité : 1 titre fort + 1 phrase + max 3 bullets par écran

---

## Roadmap des phases

**Phase 1 — Design system (FAIT)**
Enrichissement du bloc `:root`, mise à jour des composants CSS (cards, boutons, header, quote, step-num, forms, note-cards). Création de ce fichier. Aucune modification HTML.

**Phase 2 — CTAs sub-text + Illustration hero**
Ajout de `<span class="btn-sub">` sous les CTAs. Nouveau layout `.hero-cols` (2 colonnes). SVG inline : PDG en réunion avec panel "AI brief" flottant (Réunion, Interlocuteur, Objectif, Messages clés A/B/C).

**Phase 3 — ROI hub diagram + Video section premium**
SVG "Operating system du PDG" (hub 6 rituels). Refonte de la section vidéo en 2 colonnes : video card premium + 3 points clés.

**Phase 4 — Entre PDGs illustration + polish global**
SVG table ronde sur page Entre PDGs. Audit cross-pages : tokens, radius, cohérence typographique.
