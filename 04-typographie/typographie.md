# 04 · Typographie

> **Étape 4 du framework identité visuelle.** Choisir des polices lisibles et cohérentes avec l'esthétique globale.

[← Retour au sommaire](../README.md)

---

## 4.1 — Le système typographique en bref

| Police | Rôle | Présente sur |
|---|---|---|
| **Nunito Rounded** (700, 800) | Wordmark, titres, accroches | App ✅ · Landing ✅ |
| **Inter** | Texte courant, UI | App ✅ · Landing ✅ |
| **Space Grotesk** | ? (probable titres alt) | Landing ✅ uniquement ⚠️ |
| **Georgia (serif)** | — | Emails ⚠️ **(décrochage majeur)** |

> ⚠️ **Trois écarts à arbitrer** : Space Grotesk uniquement en landing, et surtout le **passage en Georgia dans les emails** qui rompt totalement avec le design system.
> Détails et arbitrages dans [07 · Audit](../07-audit-critique/audit-critique-roadmap.md).

---

## 4.2 — Nunito Rounded — la signature

### Identité
**Famille** : sans-serif géométrique aux **terminaisons arrondies**
**Auteur** : Vernon Adams (Nunito), extension Rounded
**Distribution** : Google Fonts

### Pourquoi cette police ?
- **Formes arrondies** = chaleur, accessibilité, douceur → aligné avec la valeur « chaleur »
- **Lisibilité** excellente à toutes tailles (notamment sur petits écrans)
- **Personnalité forte** sans être typée startup tech (différent de Poppins, qui est ultra-vu)
- **Multilingue solide** (caractères français complets, supporte accents et ligatures)

### Usages dans l'app
- **Wordmark** : « TempsPourTemps » en haut de la top bar, weight 800, letter-spacing 0.12em
- **Imports** : `Nunito Rounded` poids 700 et 800 (cf. `main.css` ligne 1)
- **Fallback stack** : `'Nunito Rounded', 'SF Pro Rounded', 'Avenir Next Rounded', 'Quicksand', 'Poppins', Inter, system-ui, sans-serif`

### ⚠️ Question critique : licence
> **À vérifier d'urgence** : Nunito (la base) est sous licence **SIL Open Font License 1.1** (libre, gratuite, redistribuable).
> En revanche, **« Nunito Rounded » n'est pas une police officielle Google Fonts** distincte — c'est une variante dérivée par tiers. L'import via Google Fonts (`https://fonts.googleapis.com/css2?family=Nunito+Rounded`) **renverra une 404** ou un fallback silencieux.

→ **Action requise** : vérifier ce qui est effectivement chargé sur l'app en production. Si Nunito Rounded n'existe pas dans Google Fonts, alors :
1. soit on utilise vraiment **Nunito** standard et on a fait une erreur d'import historique (à corriger)
2. soit on a une version « Rounded » téléchargée localement quelque part, qu'il faut héberger et déclarer
3. soit on bascule sur **Quicksand**, **Comfortaa**, **Mulish** ou **Poppins** qui sont des sans-serif arrondis officiellement disponibles sur Google Fonts.

Cf. [07 · Audit, recommandations urgentes](../07-audit-critique/audit-critique-roadmap.md).

---

## 4.3 — Inter — l'utilitaire

### Identité
**Famille** : sans-serif neutre conçue pour l'écran
**Auteur** : Rasmus Andersson (ex-Spotify, Figma)
**Distribution** : Google Fonts · [rsms.me/inter](https://rsms.me/inter)
**Licence** : SIL Open Font License 1.1 ✅ libre

### Pourquoi cette police ?
- **Conçue pour les écrans** : hinting parfait, lisibilité optimale à toutes tailles (10 → 60px)
- **Très large famille** (9 weights, italics, monospace) : permet de tout faire sans changer de police
- **Neutre** : laisse Nunito Rounded porter la signature
- **Standard du métier** : Figma, Linear, GitHub Mobile l'utilisent → familier pour le public néo-arrivant tech

### Usages dans l'app
- Body, paragraphes, labels, inputs, UI courante
- Min 16px sur mobile (forcé via media query ligne 384 `main.css`) pour éviter le zoom iOS sur focus

---

## 4.4 — Space Grotesk — à statuer

### Présence
Chargée dans la **landing uniquement** (cf. `layout.tsx` ligne 21) via `next/font/google`. Aucune trace dans l'app.

### Hypothèse d'usage
Probablement utilisée pour les **titres de section accrocheurs** dans la landing (typo display géométrique tendance 2023-2026), en complément de Nunito Rounded.

### Décision à prendre
Trois options :
1. **Garder Space Grotesk uniquement landing**, l'assumer comme typo « marketing/communication externe »
2. **Étendre Space Grotesk à l'app** pour les titres XL, créant un trio cohérent
3. **Retirer Space Grotesk de la landing** et tout faire avec Nunito Rounded + Inter, pour une simplicité maximale

→ **Recommandation initiale** : option 1 ou 3. L'option 2 alourdit le bundle de l'app pour un gain visuel limité.

---

## 4.5 — Hiérarchie typographique recommandée

À normaliser dans les composants. Cette hiérarchie n'est pas encore formalisée dans le code, c'est une proposition.

| Niveau | Police | Weight | Taille mobile | Taille desktop | Letter-spacing |
|---|---|---|---|---|---|
| **Display XL** (héros landing) | Nunito Rounded | 800 | 36px | 56px | -0.02em |
| **H1** (titre de page) | Nunito Rounded | 800 | 28px | 40px | -0.01em |
| **H2** (titre de section) | Nunito Rounded | 700 | 22px | 28px | normal |
| **H3** (titre de card) | Nunito Rounded | 700 | 18px | 20px | normal |
| **Body L** (intros) | Inter | 400 | 18px | 18px | normal |
| **Body** (texte courant) | Inter | 400 | 16px | 16px | normal |
| **Body S** (métadonnées) | Inter | 400 | 14px | 14px | normal |
| **Caption** (légales) | Inter | 400 | 12px | 12px | normal |
| **Wordmark** (logo) | Nunito Rounded | 800 | — | — | 0.12em (large) |
| **Eyebrow** (suréligne) | Inter ou Nunito | 600 | 11px | 11px | 0.10em (large) |

### Règles d'or
- ✅ **Jamais plus de 3 tailles** dans une même vue (sinon = bruit visuel)
- ✅ **Line-height** : 1.2 sur les titres XL, 1.4 sur les titres, 1.6 sur le corps
- ✅ **Texte justifié** : à éviter dans l'app (mauvais rendu mobile), OK dans certains emails
- ✅ **Italique** : très rare, réservé aux citations et titres d'œuvres (cf. règles francophones)

---

## 4.6 — Cas particulier : les emails

L'email du 17 juin (notre meilleur template actuel) utilise **Georgia (serif)** pour tout le contenu, ce qui est **radicalement incohérent** avec le reste de l'identité.

### Pourquoi c'est arrivé
Hypothèse : Georgia a été choisie pour le **rendu éditorial chaleureux** (le serif transmet l'écrit-à-la-main, l'intime, le personnel), idéal pour une communauté de proximité.

### Pourquoi ce n'est pas tenable
- Aucun rappel des codes de l'app → l'utilisateur ne reconnaît pas immédiatement TpT
- Georgia est typée « article de presse » / « moteur de recherche années 2000 »
- Brise la promesse de cohérence multiplateforme du framework PDF (étape 7)

### Options
1. **Migrer tous les emails sur Inter** (web-safe via fallback stack) — cohérence maximale, perte de chaleur
2. **Garder un serif mais le faire évoluer vers une vraie serif éditoriale** type **Lora**, **Source Serif Pro** ou **DM Serif Display** — chaleur éditoriale assumée + cohérence d'intention
3. **Mix Nunito Rounded (titres) + Georgia (corps)** — incohérent mais évolution douce
4. **Mix Nunito Rounded (titres) + Inter (corps)** — recommandé

→ **Recommandation** : option 4 pour cohérence + option 2 si on veut développer une « voix email » éditoriale assumée pour les communications communautaires (newsletter mensuelle).

---

## 4.7 — Anti-patterns à éviter

- ❌ **Mélanger 3 polices différentes** dans un même écran
- ❌ **Utiliser une police en italique pour de la signalétique** (mauvaise lisibilité)
- ❌ **Souligner du texte qui n'est pas un lien** (convention web universelle)
- ❌ **Texte en tout-majuscules** pour plus de 3 mots (sauf wordmark et eyebrow)
- ❌ **Polices décoratives** (Comic Sans, Lobster, Pacifico, etc.) — incompatibles avec le sérieux de la valeur « confiance »
- ❌ **Sous 14px** sur du texte lu (caption admise à 12px seulement pour mentions légales)
- ❌ **Letter-spacing négatif** sur du corps de texte (réservé aux gros titres)

---

## 4.8 — Multilangue et caractères spéciaux

L'app étant française et le public local, peu de besoins multilangues à court terme. Toutefois :
- **Accents français** : tous couverts par Inter et Nunito (à vérifier sur Nunito Rounded selon licence)
- **Apostrophe typographique** ’ (U+2019) plutôt que droite ' (U+0027) → à automatiser dans les contenus
- **Espaces insécables** avant `: ; ? !` et entre nombre et unité → respect des règles francophones

---

## Historique

| Date | Modification |
|---|---|
| 2026-06-10 | Création initiale, repérage de la divergence Nunito Rounded (licence), inventaire des polices par support |
