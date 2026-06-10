# 05 · Univers visuel

> **Étape 5 du framework identité visuelle.** Définir les éléments graphiques (pictos, photos, illustrations) qui forment l'univers cohérent et esthétique avec la personnalité de marque.

[← Retour au sommaire](../README.md)

---

## 5.1 — Principe directeur

L'univers visuel de TpT articule **trois registres complémentaires** selon le contexte d'usage :

| Registre | Quand l'utiliser | Pourquoi |
|---|---|---|
| **Photographie réelle locale** | Communications événementielles, vidéos, témoignages | Authenticité, preuve sociale, ancrage territorial |
| **Illustrations vectorielles douces** | App (états vides, onboarding), landing (sections explicatives) | Personnalité chaleureuse, marketable, déclinable |
| **Pictos géométriques minimalistes** | UI fonctionnelle de l'app | Lisibilité, sobriété, ne distrait pas de l'action |

**Règle d'or** : un seul registre dominant par écran/support. Mélanger photo + illustration + picto dans la même vue crée du bruit visuel.

---

## 5.2 — Photographie réelle locale

### Quand
- Réseaux sociaux (Instagram, Facebook)
- Vidéos témoignages et reportages de l'asso
- Landing (section « ils en parlent », hero éventuel)
- Présentations à partenaires/collectivités
- Dossiers de subvention

### Codes esthétiques
- ✅ **Cadrages serrés sur les personnes** : visages, mains, gestes d'entraide
- ✅ **Lumière naturelle** : éviter les flashs durs et les studios stériles
- ✅ **Scènes en intérieur ET extérieur** alternées (jardins, salons, marchés)
- ✅ **Diversité visible** : âges, profils, genres, origines
- ✅ **Authenticité** : pas de poses ultra-marketées, pas de « stock photos » d'inconnus souriants

### Anti-patterns
- ❌ Photos en banque d'images génériques (utilisateurs déjà vus partout)
- ❌ Filtres « instagrammables » trop saturés ou vintage
- ❌ Mise en scène trop posée (pas de poignées de main forcées, pas de regards caméra trop appliqués)
- ❌ Photos floues ou mal cadrées (même authentiques) : la qualité technique reste importante

### Traitement de couleur cohérent
- Privilégier les **tons chauds** (rappel sable/orange)
- Réduire la saturation des bleus froids
- Conserver les **tons de peau naturels** (jamais d'effet « bronzage artificiel »)
- Cohérence sur une série : appliquer le même léger preset pour qu'une story de 10 posts fonctionne comme un ensemble

### Inspirations
- Communautés visibles type **Konbini Local**, **Brut**, **La Tribu** (formats sociaux)
- Reportages photo de **Reporters d'Espoirs**
- Photographes de l'économie sociale et solidaire (les Apprentis d'Auteuil, Emmaüs, etc.)

---

## 5.3 — Illustrations vectorielles douces

### Quand
- États vides de l'app (« aucune annonce », « pas encore d'échange »)
- Onboarding (3-5 illustrations à clé)
- Sections explicatives de la landing (« comment ça marche »)
- Couvertures de section dans les emails newsletter
- Spots vidéo (motion design léger)

### Codes esthétiques
- ✅ **Trait propre, contours doux** (jamais trop fins, jamais trop épais)
- ✅ **Personnages stylisés** : visages simples (parfois sans traits du visage), corps stylisés, gestuelles lisibles
- ✅ **Palette restreinte** : marine + sable + orange brûlée + 1-2 neutres
- ✅ **Mise en scène d'interactions** : 2 personnes qui se passent quelque chose, gestes d'aide
- ✅ **Touches de quotidien** : objets simples (livre, casserole, plante, vélo) qui ancrent dans la vraie vie

### Anti-patterns
- ❌ Style « Corporate Memphis » (les illustrations à grands membres tordus utilisées par Google, Slack, etc., devenues clichés)
- ❌ Style 3D rendu (Spline, Blender) : trop tech, casse la chaleur
- ❌ Style « cartoon enfantin » : exclut les seniors et les militants
- ❌ Palette trop large (5+ couleurs vives)
- ❌ Personnages trop typés (anonymiser un peu pour favoriser l'identification)

### Inspirations cohérentes avec TpT
- **Doctolib** (mais en plus chaleureux, moins « santé »)
- **Welcome to the Jungle** (énergie + tendresse)
- **Hello Asso** (simplicité + ESS)
- **Buffer** illustrations (douces, palette restreinte)
- **Ouibus / SNCF Connect** anciens supports (rond et chaleureux)

### Production
Si DIY :
- **Figma** + plugins gratuits (Iconify, Illustrations)
- **unDraw** (open-source, personnalisable couleur unique — mais déjà très vu)
- **Storyset** by Freepik (illustrations gratuites avec choix de palette)
- **Blush** (mix and match d'illustrations)

Si freelance/budget :
- Illustrateurs sur **Dribbble** filtrés par style
- Plateformes type **Behance**, **Malt**, **Comet**
- Budget : 80-200€ par illustration custom (selon profil et complexité)

---

## 5.4 — Pictos géométriques minimalistes

### Quand
- Toute l'**UI de l'app** (navigation, actions, statuts)
- Tableaux et formulaires
- Cartes et marqueurs
- Footers et infos secondaires

### Codes esthétiques
- ✅ **Style line/outline** (trait simple, pas de remplissage en couleur)
- ✅ **Stroke uniforme** : 1.5 ou 2px selon contexte
- ✅ **Coins doux** mais pas exagérés (cohérence avec Nunito Rounded)
- ✅ **Grid 24×24** strict pour cohérence visuelle
- ✅ **Couleur héritée** du texte courant (donc marine `#183e57` par défaut)

### Bibliothèques en usage
- **Heroicons** (`i-heroicons-*`) — usage principal pour UI standard
- **Lucide Icons** — pour les catégories de services (vélo, jardin, livre…)

### Anti-patterns
- ❌ Mix de bibliothèques (Heroicons + Lucide + Material Icons + Font Awesome) → incohérence visuelle
- ❌ Pictos colorés en interface (réserver la couleur pour signifier un état)
- ❌ Émojis Unicode dans l'UI fonctionnelle (acceptable en emails communautaires)
- ❌ Pictos trop détaillés (perdent en lisibilité à <20px)

### Règle de transition
Quand on remplace un picto Heroicons par un Lucide, ou inversement, **vérifier que tout l'écran reste cohérent stylistiquement** (poids de trait, niveau de détail). Les deux bibliothèques sont compatibles esthétiquement mais pas interchangeables n'importe comment.

---

## 5.5 — Éléments graphiques d'ambiance

### Le « blob » sable du hero
La landing utilise des **formes organiques sable** (`--color-hero-blob-1: #fcdb81`, `--color-hero-blob-2: #fde6b5`) en arrière-plan du hero.

✅ À conserver et formaliser : c'est un élément de signature visuelle élégant.

### Le gradient hero
```css
--color-bg-hero: linear-gradient(180deg, #fff9ec 0%, #fff3e0 35%, #f7f6f3 100%);
```
Variation lente du sable très clair vers le crème principal. Crée une atmosphère « lever de soleil » subtile.

⚠️ Légère **divergence** avec l'app qui utilise un gradient légèrement différent (32% vs 35%, et fin sur `#f3f7fb` au lieu de `#f7f6f3`). À harmoniser.

### Texture
Le fichier `public/texture.png` (~946 Ko) existe dans l'app mais son usage actuel n'est pas clair. À investiguer (cf. [07 · Audit](../07-audit-critique/audit-critique-roadmap.md)).

### Ombres et profondeur
- Boutons primary : ombre douce marine `0 8px 16px color-mix(in srgb, var(--color-primary) 18%, transparent)`
- Cards hover : ombre marine `0 12px 24px` + glow sable
- Pas d'ombres dures, pas d'ombres très étendues type material design

---

## 5.6 — Iconographie de service (catégories)

Les services / annonces sont catégorisés (jardinage, bricolage, cuisine, transport, écoute, etc.). Chaque catégorie a (ou devrait avoir) son picto Lucide.

### Bonnes pratiques
- Un picto par catégorie de service, **toujours le même** sur toutes les vues
- Couleur : marine par défaut, parfois fond sable clair (`bg-bg-hover`)
- Taille standard : 24×24 dans les cards, 32×32 dans les en-têtes de catégorie

### À documenter
La liste complète des catégories de services + leur picto associé n'est pas formalisée dans ce doc. À extraire de `server/database/seeds/` lors d'une prochaine revue, et à intégrer ici en tableau de mapping.

---

## 5.7 — Animation et motion

### Principes
- **Subtil** : pas de bounce dramatique, pas de spin permanent
- **Court** : 150-250ms pour les transitions UI
- **Easing doux** : `ease-out` ou cubic-bezier custom (jamais `linear`)
- **Réduit avec `prefers-reduced-motion`** : tous les utilisateurs qui ont activé la préférence d'accessibilité doivent voir des animations désactivées

### Patterns autorisés
- **Fade + translate Y** (de 8px) sur l'apparition des cards
- **Scale 0.98** au pressed des boutons
- **Color transition** sur les hovers (180-200ms)
- **Pulse** sur les indicateurs de notification (très subtil)

### Patterns à éviter
- ❌ Carousels qui défilent automatiquement (perte de contrôle utilisateur)
- ❌ Animations qui bloquent l'interaction (modal qui prend 600ms à apparaître)
- ❌ Splash screens animés (sur app PWA, à éviter)
- ❌ Lottie/JSON animations gourmandes en CPU

---

## 5.8 — Conformité avec la personnalité de marque

Récap de l'alignement des choix visuels avec la personnalité (cf. [01 · Stratégie](../01-strategie/strategie-de-marque.md#5--personnalité-le-si-tpt-était-une-personne)) :

| Choix visuel | Voisin bienveillant | Animateur de quartier |
|---|---|---|
| Photos réelles locales | ✅ Authenticité, proximité | ✅ Vie de quartier visible |
| Illustrations vectorielles douces | ✅ Chaleur, accessibilité | ✅ Énergie sans agression |
| Pictos line épurés | ✅ Clarté, accessibilité tous âges | ⚠️ Neutre |
| Palette marine + sable + orange | ✅ Chaleur + ancrage rassurant | ✅ Énergie chromatique |
| Animations subtiles | ✅ Pas guindé mais respectueux | ⚠️ Plus discret qu'animé |

---

## Historique

| Date | Modification |
|---|---|
| 2026-06-10 | Création initiale, articulation des 3 registres visuels |
