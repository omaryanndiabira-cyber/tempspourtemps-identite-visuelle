# 03 · Palette de couleurs

> **Étape 3 du framework identité visuelle.** Choisir des couleurs qui reflètent les émotions à transmettre (chaleur, confiance, simplicité).

[← Retour au sommaire](../README.md)

---

## 3.1 — Vue d'ensemble

La palette de TpT articule **3 couleurs signatures** (marine, orange brûlée, jaune sable) et un système de **couleurs sémantiques** (success, danger, warning, info).

Le **trio signature** crée la reconnaissance ; le **système sémantique** assure la lisibilité fonctionnelle dans l'app.

### Récap visuel (à imaginer)

```
●●● Signature
■ Marine     #183e57   ← ancrage, confiance, titres, fond barre haute
■ Orange     #d65e1c   ← accents, CTAs secondaires, énergie
■ Sable      #fcdb81   ← lumière, focus, CTAs primaires (sur marine)

●●● Système sémantique
■ Success    #4a9d5f   ← validations, confirmations
■ Danger     #c44536   ← erreurs, actions destructives
■ Warning    #d97706   ← alertes, mises en garde
■ Info       #183e57   ← messages neutres (= marine signature)

●●● Fonds & textes
■ Bg main    #f7f6f3   ← fond principal (blanc cassé chaud)
■ Bg hover   #fdf1d7   ← survol (sable très clair)
■ Text       #183e57   ← texte courant (= marine signature)
■ Text 2     #4b5563   ← texte secondaire (gris ardoise)
```

---

## 3.2 — Couleurs signatures (détaillées)

### 🟦 Marine `#183e57`
> **Le mot-clé : ancrage.**

- **Rôle** : couleur primaire, identité de marque, texte principal
- **Émotions** : confiance, sérieux, stabilité, profondeur, professionnalisme
- **Usages** :
  - Fond de la top bar de l'app
  - Texte courant (corps de texte sur fond clair)
  - Titres principaux
  - Boutons primaires (variant `solid`)
  - Couleur de focus (en complément du sable)
- **Hover variant** : `#0f2f44` (15% plus sombre)
- **Variantes opacité** : `var(--color-primary)/10`, `/25`, etc.

### 🟧 Orange brûlée `#d65e1c`
> **Le mot-clé : énergie.**

- **Rôle** : couleur secondaire, accent dynamique, CTA d'engagement
- **Émotions** : chaleur, dynamisme, urgence positive, action
- **Usages** :
  - Highlights dans les titres (« *Échanger* du temps »)
  - Accents dans les illustrations
  - Boutons « action positive » dans les emails (variante de l'accent)
  - Badges « nouveau » / « featured »
- **Hover variant** : `#b84e17` (landing) — manque côté app, à créer
- ⚠️ **Attention contraste** : sur fond crème, contraste limite avec petit texte (cf. 3.5)

### 🟨 Jaune sable `#fcdb81`
> **Le mot-clé : lumière.**

- **Rôle** : couleur accent, focus visuel, texte sur fond marine
- **Émotions** : optimisme, douceur, soleil, accueil
- **Usages** :
  - Texte des lettres du logo
  - Texte sur fond marine (top bar, footer email, sections sombres)
  - Bordure / focus ring (`--color-focus`)
  - Background hover (`--color-bg-hover: #fdf1d7`, sable très clair)
  - Wordmark dans la top bar (`brand-wordmark`)
- **Hover variant** : `#f5cb5c` (landing) — manque côté app
- ⚠️ **Ne jamais utiliser** pour du texte sur fond clair (contraste insuffisant)

---

## 3.3 — Couleurs sémantiques (système fonctionnel)

| Token | Hex | Hover | Usage |
|---|---|---|---|
| `--color-success` | `#4a9d5f` (vert forêt) | `#3d8450` | Validations (« RDV confirmé »), créditation de temps |
| `--color-danger` | `#c44536` (rouge terracotta) | `#a83829` | Erreurs, suppression, refus |
| `--color-warning` | `#d97706` (ambre) | `#b86205` | Alertes (« attention »), expirations imminentes |
| `--color-info` | `#183e57` (= marine) | `#0f2f44` | Informations neutres |

### Choix volontaires
- **Pas de vert pomme vif** : on préfère un vert forêt qui dialogue avec le marine sans crier
- **Pas de rouge pur** : le terracotta s'inscrit dans la palette terrienne globale
- **Pas de jaune vif** pour le warning : on prend un ambre profond qui dialogue avec l'orange signature
- **Info = marine** : pas besoin d'une teinte dédiée, cohérence visuelle renforcée

### Versions « light » (10% opacité)
Toutes disponibles via `--color-success-light`, `--color-danger-light`, etc. Utilisées pour les fonds d'alertes (`bg-success/10` → bg vert très pâle pour bandeau info).

---

## 3.4 — Fonds, textes et bordures

### Fonds
| Token | Hex | Usage |
|---|---|---|
| `--color-bg-main` | `#f7f6f3` | Fond principal de l'app (blanc cassé chaud) |
| `--color-bg-secondary` | `#f3f3f5` | Fond de cards secondaires, inputs |
| `--color-bg-hover` | `#fdf1d7` | Survol (sable très clair) |
| `--color-bg-gradient` | `linear-gradient(180deg, #fff9ec 0%, #fff3e0 32%, #f3f7fb 100%)` | Hero/page principale, dégradé sable → bleu |

### Textes
| Token | Hex | Usage |
|---|---|---|
| `--color-text-main` | `#183e57` | Texte courant (= marine, choix volontaire) |
| `--color-text-secondary` | `#4b5563` | Texte secondaire (gris ardoise) |
| `--color-text-tertiary` | `#717182` | Mentions légales, métadonnées discrètes |

### Bordures
| Token | Hex | Usage |
|---|---|---|
| `--color-border-main` | `#e9ebef` | Bordure standard discrète |
| `--color-border-secondary` | `#d6dbe2` | Bordure plus marquée (cards, inputs) |

---

## 3.5 — Accessibilité (contrastes WCAG)

> **Engagement** : tout texte dans l'app doit respecter au minimum **WCAG AA** (ratio 4.5:1 pour texte normal, 3:1 pour texte large).

### Contrastes principaux validés
| Combinaison | Ratio | WCAG |
|---|---|---|
| Marine `#183e57` sur Bg main `#f7f6f3` | ~12:1 | ✅ AAA |
| Sable `#fcdb81` sur Marine `#183e57` | ~9:1 | ✅ AAA |
| Texte secondaire `#4b5563` sur Bg main | ~7.5:1 | ✅ AAA |
| Texte tertiaire `#717182` sur Bg main | ~4.7:1 | ✅ AA (texte normal) |

### ⚠️ Combinaisons à proscrire
| Combinaison | Pourquoi |
|---|---|
| Sable sur fond crème | Contraste ~1.2:1 — illisible |
| Orange `#d65e1c` sur sable `#fcdb81` | Contraste ~2.8:1 — sous AA |
| Sable sur orange | Contraste ~2.5:1 — sous AA |
| Texte tertiaire `#717182` en petit caractère (<14px) | Limite AA |

### Bonnes pratiques
- **Tester avec un outil** comme [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) avant toute nouvelle combinaison
- **Ne jamais transmettre une information uniquement par la couleur** (toujours doublé d'une icône ou d'un texte)
- **Tester en niveaux de gris** : si le rendu est lisible en N&B, c'est bon signe

---

## 3.6 — Règles d'application dans l'app

### Hiérarchie de présence
- 60% : fonds neutres (bg-main, bg-secondary, white)
- 25% : marine (texte, bordures, structures)
- 10% : sable (focus, accents, CTAs sur fond marine)
- 5% : orange brûlée (highlights ponctuels)

→ Cette répartition garantit que le marine reste l'ancrage, que le sable ressort là où il compte (focus, action), et que l'orange ne sature pas l'interface.

### Boutons (extrait du CSS app)
- **Solid primary** : fond marine + texte sable
- **Outline** : bordure marine + texte marine sur fond blanc, devient marine plein au hover
- **Bouton « neutral/black » Nuxt UI** : remplacé par dégradé orange → sable (`linear-gradient(120deg, #d65e1c → #fcdb81)`)

### Cards
- Fond blanc
- Bordure `#d6dbe2`
- **Hover** : bordure devient sable `#fcdb81` + ombre douce (élégant et cohérent avec le focus)

---

## 3.7 — Cohérence inter-supports (état actuel)

| Plateforme | Marine | Orange | Sable | Verdict |
|---|---|---|---|---|
| **App (CSS tokens)** | `#183e57` | `#d65e1c` | `#fcdb81` | ✅ source de vérité |
| **Landing (CSS tokens)** | `#183e57` | `#d65e1c` | `#fcdb81` | ✅ aligné |
| **Logo SVG** | `#28445D` | — | `#F9DA8F` | ⚠️ **divergent** (#28445D vs #183e57, #F9DA8F vs #fcdb81) |
| **Email 17 juin** | `#183e57` | — | `#fcdb81` | ✅ aligné |

### À corriger
- Le SVG du logo n'utilise pas les bons hex → soit on corrige le SVG, soit on accepte la « légère mémoire » historique (à arbitrer).
- Cf. recommandations dans [07 · Audit](../07-audit-critique/audit-critique-roadmap.md).

---

## 3.8 — Évolutions possibles (réflexions ouvertes)

À débattre dans le cadre de l'[audit critique](../07-audit-critique/audit-critique-roadmap.md) :

- **Trop chaud ?** La palette tire fort vers les ocres et le sable, parfait pour la chaleur mais peut être perçu comme « old school / asso » par certains publics. Un point ponctuel de couleur plus moderne (un teal/menthe, un fuchsia) pourrait rajeunir sans dénaturer.
- **Manque de vert vif** : un vert plus saturé pourrait incarner « croissance, communauté qui grandit » (à explorer pour les communications événementielles).
- **Mode sombre** : aucun token n'est défini pour un dark mode. Les utilisateurs qui ont leur OS en sombre voient une app en clair forcée. Décision à prendre (cf. roadmap).

---

## Historique

| Date | Modification |
|---|---|
| 2026-06-10 | Création initiale, audit des divergences avec landing/logo/email |
