# 06 · Supports & déclinaisons

> **Étape 7 du framework identité visuelle** : « cohérence visuelle sur tous les supports » (multiplateforme, déclinable, évolutif).

[← Retour au sommaire](../README.md)

---

## 6.1 — Cartographie actuelle des supports

| Support | État | Source de vérité | Cohérence avec design system |
|---|---|---|---|
| **App web (Nuxt 4)** | ✅ Production | `app/assets/css/main.css` | ✅ référence |
| **Landing (Next.js)** | ✅ Production | `src/app/globals.css` | ✅ ~99% aligné (gradient et borders légèrement divergents) |
| **Emails transactionnels (app)** | ⚠️ Existent | `server/utils/brevo.ts` + templates inline | ❌ Pas alignés (template à reconstruire) |
| **Emails communautaires** | ⚠️ Ad-hoc | `~/Downloads/email_*.html` | ❌ Décrochage typo (Georgia) |
| **Print (flyers, affiches)** | ❌ Aucun | — | — |
| **Réseaux sociaux** | ❌ Templates inexistants | — | — |
| **Push notifications (OneSignal)** | ✅ Production | `server/utils/onesignal.ts` | ⚠️ Pas de personnalisation visuelle |
| **PDF (dossiers partenaires)** | ❌ Aucun template | — | — |
| **Goodies / merch** | ❌ Aucun | — | — |

→ **Constat global** : très bonne cohérence sur les supports digitaux primaires (app + landing), mais **lacunes structurelles** sur tout ce qui sort de l'écran (print, RS, emails).

---

## 6.2 — Web / App

### Principes de cohérence
- Source de vérité **unique** : `app/assets/css/main.css` (CSS variables)
- Tous les composants `App*` (AppButton, AppInput, AppModal, AppFormOverlay) doivent **uniquement** consommer ces variables
- **Jamais** de couleur brute Tailwind (`text-orange-500`, `bg-blue-400`) — uniquement des tokens sémantiques

### Convention de routing visuelle
- Les **formulaires de création/édition** (annonce, activité, RDV) passent par `AppFormOverlay` (bottom sheet mobile / modal desktop). **Jamais** en page pleine. C'est un choix d'identité fonctionnelle aussi.

### Mobile-first non-négociable
- Tester à 375px (iPhone SE), 768px (tablet), 1024px+ (desktop)
- Touch targets ≥ 44×44px
- Font-size min 16px sur inputs mobile (évite le zoom iOS)

### Performance visuelle
- `loading="lazy"` sur toutes les images sous la ligne de flottaison
- WebP/AVIF via Supabase Storage transforms
- Pas de Lottie/JSON lourd dans l'UI critique

→ Cf. [04 · Typographie](../04-typographie/typographie.md) et [03 · Couleurs](../03-couleurs/palette-couleurs.md) pour les valeurs exactes.

---

## 6.3 — Landing page

Repo séparé : `tempspourtemps-landing` (Next.js + Tailwind).

### Différences délibérées vs app
- **Espacements plus généreux** (objectif : marketing/séduction)
- **Présence du gradient hero** plus marquée
- **Possibilité d'illustrations vectorielles** custom (les états vides de l'app étant moins « hero »)
- **Possibilité d'animation entrée** sur le scroll (subtile)

### Différences accidentelles vs app (à corriger)
- Border `#e0ddd6` (landing) vs `#e9ebef` (app) — divergence de quelques pixels chromatiques
- Gradient hero stop intermédiaire à 35% (landing) vs 32% (app)
- Couleur de fin du gradient `#f7f6f3` (landing) vs `#f3f7fb` (app) — **l'app a un fin bleuté, la landing reste crème** ⚠️
- Présence de Space Grotesk (landing) absente dans l'app

→ Voir recommandations dans [07 · Audit](../07-audit-critique/audit-critique-roadmap.md).

---

## 6.4 — Emails

Sous-dossier dédié : **[`./emails/`](./emails/)**.

Contient :
- L'exemple actuel (`exemple-email-cloture-17juin.html`)
- Le README qui formalise un **template canonique** à partir de cet exemple

### Synthèse rapide
- **Largeur max 560px** (compatible Outlook, Gmail mobile, Apple Mail)
- **Tableau HTML inline** (pas de CSS externe ni Flexbox/Grid)
- **Border-radius 12px** sur conteneur principal, **10px** sur blocks internes
- **Header marine + texte sable** = signature de marque
- **Banner date jaune sable** = mise en relief événementielle
- **Body sur fond crème clair** (#f5f0e8 ou #fdf6e3)
- **Blocks à border-left colorée** (sable ou marine selon hiérarchie)
- **Footer marine + signature en sable**

⚠️ **Le template actuel utilise Georgia** : voir l'arbitrage à faire dans [04 · Typographie](../04-typographie/typographie.md#46--cas-particulier--les-emails).

---

## 6.5 — Print (à créer)

### Formats prioritaires

| Format | Usage | Quantité estimée |
|---|---|---|
| **Flyer A6** (105×148mm) | Distribution boîtes aux lettres, accueil mairie | 1000-5000 par diffusion |
| **Affiche A3** (297×420mm) | Vitrines commerçants, panneaux assos | 30-100 par campagne |
| **Carte de visite** (85×55mm) | Bénévoles, événements | 500-1000 |
| **Kakemono / roll-up** (85×200cm) | Stands événements (forum asso, marché) | 1-2 |

### Spécifications techniques
- **Profil couleur** : CMJN (jamais RGB pour le print)
- **Conversion couleurs** : à valider avec l'imprimeur (les hex web rendent légèrement différemment en CMJN)
  - Marine `#183e57` → approximation CMJN `C85 M65 J40 N40`
  - Orange `#d65e1c` → approximation CMJN `C0 M75 J95 N5`
  - Sable `#fcdb81` → approximation CMJN `C0 M15 J55 N0`
- **Résolution** : 300dpi minimum sur les images
- **Marges de coupe (fond perdu)** : 3mm minimum
- **Polices** : exporter en outlines (vectoriser) avant envoi à l'imprimeur
- **Fichier** : PDF/X-1a ou PDF/X-4

### À produire (templates Figma ou Illustrator)
- [ ] Template flyer A6 recto/verso
- [ ] Template affiche A3
- [ ] Template carte de visite
- [ ] Template kakemono
- [ ] Bibliothèque d'éléments print (pictos catégories vectorisés)

---

## 6.6 — Réseaux sociaux (à créer)

### Formats par plateforme

| Plateforme | Format clé | Dimensions |
|---|---|---|
| **Instagram post** | Carré | 1080×1080 |
| **Instagram story** | Vertical | 1080×1920 |
| **Instagram reel cover** | Vertical | 1080×1920 |
| **Facebook post** | Paysage | 1200×630 |
| **Facebook cover** | Paysage large | 1640×624 |
| **LinkedIn post** | Carré ou paysage | 1200×1200 ou 1200×627 |
| **LinkedIn cover entreprise** | Paysage très large | 1128×191 |
| **YouTube vignette** | Paysage | 1280×720 |

### Templates types à créer
- [ ] Annonce d'événement (date + lieu + visuel)
- [ ] Témoignage utilisateur (citation + photo)
- [ ] Chiffre clé (KPI mis en avant)
- [ ] Recrutement bénévoles
- [ ] Actu / news (article ou réflexion)
- [ ] Carrousel pédagogique (« comment ça marche en 3 swipes »)

### Outil recommandé
**Figma** (gratuit) avec un fichier `tempspourtemps-rs-templates` qui contient toutes les variantes.

### Règles
- **Cohérence par série** : pas de mix random de pictos, illustrations, photos
- **Réserver le coin haut-droit** au logo (toujours au même endroit dans la grille)
- **Texte lisible sans le visuel** : si on coupe l'image, le texte doit suffire
- **Format vertical 9:16** quasi-obligatoire en 2026 (Stories, Reels, Shorts, TikTok)

---

## 6.7 — Push notifications

OneSignal envoie les notifs avec :
- **Icône** : actuellement `icon-192x192.png` (le monogramme tpt)
- **Image hero** (optionnelle) : pas exploitée
- **Couleur de marque** : à configurer dans le dashboard OneSignal (`#183e57`)

### Recommandations
- Configurer la **brand color** OneSignal sur marine `#183e57`
- Sur Android, utiliser une **icône silhouette blanche** (Android dessine en blanc forcé dans la status bar)
- Pour les notifs importantes (RDV imminent, nouvel échange), tester l'ajout d'une **hero image** : illustration vectorielle, format 2:1, max 50Ko

→ À documenter quand un standard sera arrêté.

---

## 6.8 — Goodies / merchandising (vision long terme)

À évaluer quand la communauté grandit (>500 membres actifs) :
- **Stickers** (logo monogramme + slogan)
- **Tote bag** (logo + URL)
- **T-shirts bénévoles** (logo poitrine + dos sloganisé)
- **Mugs** (offerts aux nouveaux inscrits actifs)
- **Carnets** (carnet de temps : « j'ai donné X heures, j'ai reçu Y »)

### Règles
- **Toujours le logo dans sa couleur officielle** ou en monochrome (jamais sable seul sans fond marine)
- **Pas de slogans à la mode** qui dateront en 2 ans
- **Producteurs locaux ou ESS** quand possible (cohérence avec les valeurs)
- **Quantités raisonnables** (le but n'est pas de remplir le bureau, mais de récompenser/identifier)

---

## 6.9 — Carte de cohérence à vérifier avant chaque production

> Avant de publier ou imprimer **quoi que ce soit**, parcourir cette checklist.

- [ ] Le **logo** est dans une de ses variantes officielles (cf. [02 · Logo](../02-logo/logo.md))
- [ ] Les **couleurs** utilisent les hex officiels (cf. [03 · Palette](../03-couleurs/palette-couleurs.md))
- [ ] La **typographie** respecte la hiérarchie recommandée (cf. [04 · Typographie](../04-typographie/typographie.md))
- [ ] Les **pictos/illustrations** respectent un seul registre (cf. [05 · Univers visuel](../05-univers-visuel/univers-visuel.md))
- [ ] Le **ton** est aligné avec la personnalité (cf. [01 · Stratégie](../01-strategie/strategie-de-marque.md))
- [ ] Sur les supports digitaux : les **contrastes** respectent WCAG AA
- [ ] Sur les supports print : les **couleurs sont en CMJN** et les **polices sont vectorisées**

---

## Historique

| Date | Modification |
|---|---|
| 2026-06-10 | Création initiale, cartographie des supports, identification des lacunes print et RS |
