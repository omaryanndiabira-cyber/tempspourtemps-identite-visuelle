# Identité visuelle — Temps pour Temps

> **Espace documentaire centralisé** de l'identité visuelle de Temps pour Temps (TpT), plateforme d'échange de temps et d'entraide entre voisins.
> Rédigé le 2026-06-10. À considérer comme la **source de vérité** pour toute production visuelle (app, landing, emails, print, réseaux sociaux).

---

## En bref

| | |
|---|---|
| **Nom** | Temps pour Temps (TpT) |
| **Promesse** | « Échangez du temps, pas de l'argent » |
| **Mission** | Reconnecter le voisinage par l'entraide concrète |
| **Personnalité** | Voisin·e bienveillant·e + animateur·rice de quartier |
| **Couleurs signatures** | Marine `#183e57` · Orange brûlée `#d65e1c` · Jaune sable `#fcdb81` |
| **Typographies** | Nunito Rounded (titres, wordmark) + Inter (texte courant) |
| **Maturité actuelle** | Identité fonctionnelle mais provisoire — voir [audit critique](./07-audit-critique/audit-critique-roadmap.md) |

---

## Sommaire de l'espace documentaire

### 📐 Fondations (le « pourquoi »)
- **[01 · Stratégie de marque](./01-strategie/strategie-de-marque.md)** — mission, valeurs, cible, personnalité, ton, promesse
- **[07 · Audit critique & roadmap](./07-audit-critique/audit-critique-roadmap.md)** — état des lieux honnête, benchmark concurrentiel, recommandations priorisées, scénarios DIY / freelance / agence

### 🎨 Éléments graphiques (le « quoi »)
- **[02 · Logo](./02-logo/logo.md)** — description, variantes, règles d'usage, exclusion zone
- **[03 · Palette de couleurs](./03-couleurs/palette-couleurs.md)** — tokens, sémantique, accessibilité, usages
- **[04 · Typographie](./04-typographie/typographie.md)** — Nunito Rounded + Inter, hiérarchie, licences
- **[05 · Univers visuel](./05-univers-visuel/univers-visuel.md)** — illustrations, pictos, photos, mood

### 🧱 Déclinaisons (le « où »)
- **[06 · Supports & déclinaisons](./06-supports/declinaisons-supports.md)** — web/app, print, réseaux sociaux, emails
  - **[Template email canonique](./06-supports/emails/README.md)** — extraction et règles à partir de l'email du 17 juin

### 📎 Assets bruts
- **[`assets/logo/`](./assets/logo/)** — PNG (avec / sans fond), SVG, favicon, icône PWA
- **[`assets/references/`](./assets/references/)** — framework PDF d'identité visuelle (source : AELF), références externes

---

## Comment utiliser ce dossier

1. **Avant toute nouvelle production visuelle** (post LinkedIn, flyer mairie, mockup, nouvelle page) : commencer par la stratégie de marque (01) pour vérifier l'alignement avec la mission/personnalité.
2. **Pour une question technique précise** (« quelle couleur pour un bouton danger ? », « quel weight pour un titre de section ? ») : aller directement dans le doc concerné (02 à 06).
3. **Si on hésite sur la conformité de quelque chose** : se référer à l'audit (07) qui répertorie les écarts connus entre app, landing et emails — et l'arbitrage à faire.
4. **Quand on modifie un élément du design system** (palette, typo, logo) : mettre à jour le doc correspondant **et** consigner la décision dans la section « Historique » du doc concerné.

---

## Cycle de vie de ce document

Ce dossier est **vivant**. Il sera enrichi à chaque grande étape :
- **Phase actuelle** : audit et formalisation de l'existant (juin 2026)
- **Phase suivante** : décisions stratégiques (challenger palette ? embaucher un freelance ? cf. roadmap dans 07)
- **Phase d'industrialisation** : production de templates print + RS + nouveau logo si décidé

**Dernière mise à jour** : 2026-06-10

---

## Méthode et sources

Ce document s'appuie sur le framework présenté dans `assets/references/framework-identite-visuelle-aelf.pdf` (les 6 éléments constitutifs, les 6 étapes de création, les 3 critères de pérennité : multiplateforme / déclinable / évolutif).

Les analyses techniques de l'existant se basent sur :
- `app/assets/css/main.css` du repo `tempspourtemps-stseb` (design system app)
- `src/app/globals.css` du repo `tempspourtemps-landing` (landing)
- `~/Downloads/email_cloture_17juin.html` (template email best-effort actuel)
- Assets bruts dans `public/` du repo de l'app
