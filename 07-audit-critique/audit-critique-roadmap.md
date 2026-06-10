# 07 · Audit critique & roadmap stratégique

> **Document stratégique** : état des lieux honnête, benchmark concurrentiel, alternatives, roadmap chiffrée.
> Rédigé pour servir de **base de décision** sur l'évolution de l'identité visuelle de Temps pour Temps.

[← Retour au sommaire](../README.md)

---

## 📋 Sommaire du document

1. [Audit factuel — où en est-on ?](#1--audit-factuel)
2. [Forces / faiblesses / opportunités / menaces](#2--swot-visuel)
3. [Cartographie des écarts](#3--cartographie-des-écarts-incohérences-techniques)
4. [Benchmark concurrentiel](#4--benchmark-concurrentiel)
5. [Alternatives à explorer](#5--alternatives-à-explorer-palette-typo-direction-créa)
6. [Roadmap chiffrée (3 scénarios)](#6--roadmap-chiffrée--3-scénarios)
7. [Recommandation finale](#7--recommandation-finale)

---

## 1 · Audit factuel

### Note globale : **6.5 / 10**

> Une identité visuelle **fonctionnelle, lisible et cohérente sur ses supports primaires** (app + landing), mais **fragile structurellement** (logo non définitif, polices à statuer, supports secondaires inexistants).

### 1.1 — Ce qui fonctionne ✅

| Élément | Pourquoi ça fonctionne |
|---|---|
| **Palette signature** marine + sable + orange brûlée | Trio chaleureux et différenciant, équilibré entre confiance (marine) et énergie (orange/sable). Pas trop vu. |
| **Système de tokens CSS** | Architecture saine, source de vérité unique pour l'app. Permet des évolutions sans casser tout. |
| **Cohérence app ↔ landing** | ~99% alignée, ce qui est très rare en early-stage. Le code des deux apps respecte le design system. |
| **Choix de Nunito + Inter** | Bonne intention : rondeur signature + neutralité fonctionnelle. Le combo « display rounded + sans utility » est éprouvé. |
| **Accessibilité contraste** | Marine sur crème = 12:1 (AAA). Le contraste primaire est excellent. |
| **Mobile-first** | Le design system intègre les contraintes mobiles (font min 16px sur inputs, touch targets, safe areas). |
| **Sémantique des couleurs** | Distinction signature (3 couleurs) vs fonctionnelles (success/danger/warning/info). Permet d'évoluer sans casser le sens. |

### 1.2 — Ce qui ne fonctionne pas ❌

| Élément | Pourquoi ça ne fonctionne pas |
|---|---|
| **Logo non définitif assumé** | Tout le branding repose sur un logo que le créateur considère provisoire. Risque d'avoir à tout refaire dans 6 mois. |
| **Couleurs du SVG logo ≠ tokens CSS** | `#28445D` vs `#183e57` ; `#F9DA8F` vs `#fcdb81`. Petite mais réelle dette. |
| **Polices d'email** | Georgia (serif) dans les emails communautaires, totalement détachée du design system. |
| **« Nunito Rounded » potentiellement invalide** | L'import Google Fonts pour « Nunito Rounded » ne renverra peut-être qu'un fallback silencieux. À vérifier en prod. |
| **Pas de wordmark vectoriel séparé** | Si on veut écrire « Temps pour Temps » en grand, on n'a pas de SVG dédié, juste du texte CSS. |
| **Aucune variante monochrome du logo** | Pas de version pour photocopies, tampons, gravures, fonds très chargés. |
| **Pas de templates print** | Flyers, affiches, cartes de visite à faire from scratch à chaque besoin. |
| **Pas de templates RS** | Instagram/Facebook/LinkedIn = page blanche à chaque post. |
| **Pas d'illustrations propres** | États vides, onboarding, sections explicatives = libre de droits génériques (unDraw, etc.) ou rien. |
| **Nom écrit différemment** | « Temps pour Temps » (officiel) vs « TempsPourTemps » (email + code) vs « TpT » (acronyme). |
| **Pas de dépôt INPI** | La marque n'est pas protégée. Risque si essaimage hors St-Sébastien. |
| **Pas de mode sombre** | Les utilisateurs OS sombre voient l'app forcée en clair. |
| **`texture.png` (946 Ko) dans `public/`** | Asset énorme dont l'usage actuel n'est pas clair. Dette de bundle. |

### 1.3 — Ce qui est moyen / à challenger ⚠️

| Élément | Question ouverte |
|---|---|
| **Palette globalement chaude** | Risque de « old school / asso » selon le public. Un accent froid (teal, menthe) pourrait rajeunir sans dénaturer. |
| **Orange brûlée peu utilisée** | Présente dans les tokens mais peu visible dans l'UI. Quel rôle réel ? |
| **Personnalité « voisin + animateur »** | Difficile à incarner si pas de mascotte / vrai porte-parole visuel. Faut-il introduire un personnage emblème ? |
| **Logo monogramme « tpt »** | Lisible mais ne raconte pas l'histoire d'échange. Pas immédiatement parlant. |
| **3 polices dans la landing** | Nunito + Inter + Space Grotesk. Pourquoi cette 3ème ? Décision oubliée ou délibérée ? |

---

## 2 · SWOT visuel

```
┌───────────────────────────────────────┬───────────────────────────────────────┐
│            FORCES (intérieur)         │         FAIBLESSES (intérieur)        │
├───────────────────────────────────────┼───────────────────────────────────────┤
│ • Tokens CSS bien architecturés       │ • Logo provisoire, pas de plan B clair│
│ • Couleurs distinctives et chaudes    │ • Polices d'email décrochées          │
│ • Cohérence app ↔ landing             │ • Pas de variantes mono / wordmark     │
│ • Accessibilité contraste excellente  │ • Aucun template print / RS           │
│ • Mobile-first dans le DNA            │ • Marque non déposée                  │
│ • Promesse claire (« temps, pas       │ • Pas de mode sombre                  │
│   d'argent »)                         │ • Nom écrit incohéremment             │
└───────────────────────────────────────┴───────────────────────────────────────┘
┌───────────────────────────────────────┬───────────────────────────────────────┐
│           OPPORTUNITÉS (extérieur)    │           MENACES (extérieur)         │
├───────────────────────────────────────┼───────────────────────────────────────┤
│ • Concurrents (Accorderie, SEL) avec  │ • Si essaimage rapide : risque que la │
│   identités datées → différenciation  │   marque locale soit copiée/diluée    │
│ • Vague « low-tech / ESS / quartiers  │ • Risque de devoir tout refaire si    │
│   apaisés » porteuse                  │   un partenaire institutionnel        │
│ • Communauté grandissante = corpus    │   exige un branding professionnel     │
│   photo authentique à constituer      │ • Trend visuel actuel (chaud, ocre)   │
│ • Subventions ESS = besoin de         │   peut sembler « 2024-2026 » dans     │
│   dossiers visuels professionnels     │   3-5 ans                             │
│ • Saisonnalité (printemps =           │ • Si Nunito Rounded n'existe pas      │
│   communications jardins, automne =   │   officiellement = bug silencieux     │
│   communications cocooning)           │   à corriger en urgence               │
└───────────────────────────────────────┴───────────────────────────────────────┘
```

---

## 3 · Cartographie des écarts (incohérences techniques)

> Vue exhaustive de toutes les **divergences** détectées entre les trois supports principaux (app, landing, email).

| Aspect | App | Landing | Email | Verdict | Priorité |
|---|---|---|---|---|---|
| Marine | `#183e57` | `#183e57` | `#183e57` | ✅ aligné | — |
| Sable | `#fcdb81` | `#fcdb81` | `#fcdb81` | ✅ aligné | — |
| Marine logo SVG | — | — | — | ❌ `#28445D` divergent | 🟡 Moyenne |
| Sable logo SVG | — | — | — | ❌ `#F9DA8F` divergent | 🟡 Moyenne |
| Border | `#e9ebef` | `#e0ddd6` | n/a | ⚠️ ~5 unités d'écart | 🟢 Faible |
| Gradient hero stop | 32% | 35% | n/a | ⚠️ 3 points d'écart | 🟢 Faible |
| Gradient hero fin | `#f3f7fb` (bleuté) | `#f7f6f3` (crème) | n/a | ❌ teintes différentes | 🟡 Moyenne |
| Police titre | Nunito Rounded | Nunito Rounded | Georgia | ❌ Email décroché | 🔴 Haute |
| Police body | Inter | Inter | Georgia | ❌ Email décroché | 🔴 Haute |
| 3ème police | — | Space Grotesk | — | ⚠️ Uniquement landing | 🟡 Moyenne |
| Bg body | `#f7f6f3` | `#f7f6f3` | `#f5f0e8` | ⚠️ Email plus jaune | 🟢 Faible |
| Block highlight bg | `bg-hover #fdf1d7` | n/a | `#fdf6e3` | ⚠️ Variations sable | 🟢 Faible |
| Radius cards | `1.5rem` (24px)¹ | `1.5rem` (24px) | `12px` (header), `10px` (blocks) | ⚠️ Différents | 🟢 Faible |
| Radius bouton | (variable) | `9999px` (pill) | `9999px` (recommandé) | ⚠️ Pas explicite app | 🟡 Moyenne |
| Wordmark | « TempsPourTemps » | « Temps pour Temps » | « TempsPourTemps » | ❌ Casse incohérente | 🔴 Haute |

¹ Pas explicite dans le CSS de l'app — à vérifier composant par composant.

### Recommandations de correction

#### 🔴 Priorité haute (à faire avant tout essaimage / dossier presse)
1. **Trancher l'orthographe officielle du nom** : « Temps pour Temps » (officiel) ou « TempsPourTemps » (compact) ? Décision et application partout.
2. **Reconstruire le système d'emails** pour utiliser Inter (+ éventuelle Nunito Rounded pour titres). Industrialiser via template engine.
3. **Vérifier en production** que « Nunito Rounded » se charge bien. Sinon, basculer sur Nunito standard ou Quicksand.

#### 🟡 Priorité moyenne (à faire dans les 3 mois)
4. **Corriger les hex du SVG logo** pour matcher les tokens CSS (`#28445D` → `#183e57`, `#F9DA8F` → `#fcdb81`).
5. **Aligner les fins de gradient** hero entre app et landing.
6. **Décider du sort de Space Grotesk** (retirer ou étendre).
7. **Formaliser le radius bouton** dans le CSS de l'app (`9999px` pour pill ou `0.75rem` pour rounded ?).

#### 🟢 Priorité faible (à faire à l'occasion d'un refactor)
8. Harmoniser bordures `#e9ebef` ↔ `#e0ddd6`.
9. Harmoniser les nuances de sable dans les bg secondaires.

---

## 4 · Benchmark concurrentiel

### 4.1 — Acteurs comparés

| Acteur | Type | Audience | Force visuelle | Faiblesse visuelle |
|---|---|---|---|---|
| **Accorderie** | Réseau franco-québécois banque de temps | Mixte intergén. | Présent depuis 1990s, ancré | Identité datée, peu de cohérence inter-accorderies |
| **SEL (Systèmes d'Échange Local)** | Réseau historique français | Plutôt seniors / militants | Présence ESS | Pas d'identité unifiée, chaque SEL fait son site |
| **Time Republik / TimeBanks USA** | International | Diaspora urbaine | Codes tech / SaaS modernes | Froid, anglais, perd la dimension voisinage |
| **Allo-Voisins** | Marketplace services voisinage | Familles | Branding moderne, app léchée | Monétaire, codes commerciaux |
| **MyTroc / Tribee** | Plateformes troc | Jeunes urbains | Direction artistique colorée | Manque sérieux institutionnel |
| **Bénévolt'** / **Tous Bénévoles** | Mise en relation bénévolat | Tous publics | Codes assos lisibles | Pas excitant visuellement |
| **Indy / KissKissBankBank** | Financement ESS | 25-45 ans CSP+ | Identité contemporaine forte | Très tech, perd le côté quartier |

### 4.2 — Notre positionnement sur la carte visuelle

```
                     CHALEUREUX
                          ↑
            ┌─────────────┼─────────────┐
            │  Accorderie │   Tous Bén. │
            │      ●      │      ●      │
            │             │             │
ASSO ──────┼─────────────┼─────────────┼──── COMMERCIAL
            │             │             │
            │   Time Rep. │   Allo-Vois.│
            │      ●      │      ●      │
            │             │             │
            │  ← →  ★ TpT zone visée    │
            │      (chaleureux + moderne+│
            │       asso assumé)         │
            └─────────────┼─────────────┘
                          ↓
                       FROID
```

**Constat** : la zone « chaleureux + moderne + asso assumé » est **peu occupée**. C'est la niche visuelle naturelle de TpT — il faut l'incarner pleinement.

### 4.3 — Ce qu'on peut emprunter / éviter

| Acteur | À emprunter | À éviter |
|---|---|---|
| **Accorderie** | Le sérieux institutionnel de la signature | Le logo daté années 90 |
| **Hello Asso** | La direction art conviviale | Le « tout-monde » qui dilue l'identité |
| **Welcome to the Jungle** | L'énergie + tendresse des illustrations | La typo trop typée tech |
| **Konbini Local** | L'authenticité photo des reportages | L'écriture journalistique trop urbaine |
| **Doctolib** | La clarté UI fonctionnelle | La froideur médicale |

---

## 5 · Alternatives à explorer (palette, typo, direction créa)

### 5.1 — Palette : 3 alternatives à explorer

#### Alt A · Garder + un point froid (recommandé)
> Ajouter une **5ème couleur signature** : un teal/canard (`#2a8c8c` env.) pour insuffler un point de fraîcheur et de modernité sans dénaturer.

```
Marine #183e57 │ Sable #fcdb81 │ Orange #d65e1c │ + Teal #2a8c8c
```

**Avantages** : moderne sans renier l'identité. Le teal dialogue bien avec le marine (parenté bleu-vert).
**Risques** : ajoute de la complexité, à doser avec parcimonie.

#### Alt B · Recentrer sur marine + sable
> Faire de l'orange brûlée une couleur **accent ponctuel** (5% max) et asseoir l'identité sur le duo marine + sable.

**Avantages** : signature plus forte, mémorisation accrue (deux couleurs c'est plus identifiable que trois).
**Risques** : perte de chaleur si on retire trop l'orange.

#### Alt C · Inverser la dominance
> Faire du **sable** la couleur dominante (60%) et du **marine** la couleur d'accent (25%). Plus chaud, plus lumineux.

**Avantages** : encore plus chaleureux, plus solaire.
**Risques** : plus difficile pour la lisibilité corporate, peut paraître trop décontracté.

→ **Recommandation initiale** : tester l'**Alt A** sur 1-2 sections de l'app pour évaluer.

### 5.2 — Typographie : 3 alternatives à explorer

#### Alt A · Conserver Nunito Rounded (si licence OK)
> Garder le combo actuel + clarifier la licence + ajouter weights manquants (400, 600).

#### Alt B · Migrer sur Quicksand ou Comfortaa
> Si Nunito Rounded n'est pas distribué proprement, **Quicksand** (Google Fonts, libre) ou **Comfortaa** (Google Fonts, libre) sont des alternatives sans-serif arrondies tout aussi qualitatives.

#### Alt C · Migrer sur une typo « custom-feel »
> **Recoleta** (chaleureuse, semi-serif), **Fraunces** (variable, expressive), **DM Sans + DM Serif Display** (combo gratuit puissant), **Plus Jakarta Sans** (récente, fraîche).

→ **Recommandation initiale** : **Alt A** si possible, sinon **Alt B** (Quicksand), avec test rapide en parallèle de **Plus Jakarta Sans** pour comparer.

### 5.3 — Logo : 3 directions créatives à explorer

#### Direction 1 · Garder le monogramme, le styliser
> Reprendre la forme `tpt` actuelle mais la **redessiner par un illustrateur** : typo custom, vraie patte. Le cercle du `p` peut devenir un symbole signature plus appuyé (un cœur stylisé ? une montre ? un soleil ?).

**Budget estimé** : 600-1500€ (freelance illustrateur typo).

#### Direction 2 · Wordmark long + symbole simple
> « Temps pour Temps » écrit en plein + un petit symbole minimaliste à côté (cercle qui s'ouvre, deux flèches qui s'échangent, sablier stylisé).

**Budget estimé** : 1000-2500€ (freelance designer).

#### Direction 3 · Repenser à partir d'un concept fort
> Brief : que le logo **raconte l'histoire de l'échange** (et pas juste les initiales). Hypothèses : sablier coupé en deux, deux cercles qui se touchent, deux mains stylisées, etc.

**Budget estimé** : 2500-6000€ (agence de design ou freelance senior).

→ **Recommandation initiale** : **Direction 1** à 12-18 mois (quand la communauté sera plus mature et qu'on saura ce qui résonne).

---

## 6 · Roadmap chiffrée — 3 scénarios

### Scénario A · DIY (0-500€)
> Tout par soi-même, outils gratuits, pas de prestataire.

| Phase | Action | Outil | Effort | Coût |
|---|---|---|---|---|
| Mois 1 | Corriger les divergences techniques (hex SVG, alignement gradient, harmoniser borders) | VS Code, Figma | 6h | 0€ |
| Mois 1 | Arbitrer l'orthographe du nom + appliquer partout | Recherche globale | 2h | 0€ |
| Mois 1 | Vérifier le chargement réel de Nunito Rounded en prod, bascule si besoin | DevTools | 3h | 0€ |
| Mois 2 | Reconstruire le template email canonique (avec Inter) | Figma + HTML | 12h | 0€ |
| Mois 2 | Industrialiser dans `server/utils/brevo.ts` | Code | 8h | 0€ |
| Mois 2-3 | Créer 6 illustrations vectorielles (états vides + onboarding) | Figma + Storyset/unDraw retouché | 20h | 0€ |
| Mois 3 | Créer 5-10 templates RS (Instagram, FB, LinkedIn) | Figma / Canva | 16h | 0€ |
| Mois 3 | Créer 3 templates print (flyer A6, affiche A3, carte visite) | Figma → export PDF/X | 12h | 0€ |
| Mois 3 | Constituer une banque photo communauté (10-20 photos sourcées) | Téléphone + retouches | 15h | 50€ matériel |
| Mois 4 | Documenter le tout dans un Notion/Figma de référence | Notion | 8h | 0€ |
| Mois 4 | Déposer la marque à l'INPI (classes pertinentes) | inpi.fr | 2h | ~250€ |
| **TOTAL** | | | **~104h** | **~300€** |

**Avantages** : zéro dépense, contrôle total, apprentissage.
**Inconvénients** : prend ~25h de travail concentré par mois, risque d'amateurisme sur certains livrables (illustrations notamment).
**Verdict** : envisageable si le porteur a la fibre design et veut maîtriser.

---

### Scénario B · Freelance ciblé (1500-5000€)
> Garder l'existant, déléguer ce qui demande une vraie expertise.

| Phase | Action | Prestataire | Effort interne | Coût externe |
|---|---|---|---|---|
| Mois 1 | Corriger divergences techniques + nom + email engine | Soi-même + dev | 20h | 0€ |
| Mois 1-2 | Briefer un freelance illustrateur pour 6-8 illustrations vectorielles cohérentes | Dribbble / Malt | 4h brief | 600-1500€ |
| Mois 2 | Briefer un freelance graphiste pour kit print (flyer A6 + affiche A3 + carte de visite + roll-up) | Malt / Comet | 4h brief | 800-1500€ |
| Mois 2 | Briefer le même graphiste pour kit RS (10 templates Figma multi-formats) | Idem | 2h brief | 400-800€ |
| Mois 3 | Audit logo par un designer senior (avis pro sur conservation/refonte) | Malt / Comet | 2h | 200-400€ |
| Mois 3 | Si refonte logo décidée : commander la direction 1 (monogramme stylisé) | Idem | 4h itérations | 600-1500€ |
| Mois 3 | INPI | Soi-même | 2h | 250€ |
| Mois 4 | Documenter et industrialiser | Soi-même | 12h | 0€ |
| **TOTAL** | | | **~50h** | **~3000-6500€** |

**Avantages** : qualité pro sur les livrables stratégiques, plus rapide, libère du temps pour le métier.
**Inconvénients** : nécessite un budget, dépendance ponctuelle aux prestas.
**Verdict** : **recommandé** si une subvention/levée le permet, ou si le coût-bénéfice du temps gagné se justifie.

---

### Scénario C · Refonte complète par agence (15 000-50 000€)
> Reprendre l'identité de zéro avec une agence de branding.

| Phase | Action | Prestataire | Effort interne | Coût externe |
|---|---|---|---|---|
| Mois 1 | Sélection agence (3 devis) | — | 8h | 0€ |
| Mois 2-3 | Brand strategy workshop (mission, vision, valeurs, positioning) | Agence | 16h | 3 000-8 000€ |
| Mois 3-4 | Création identité (logo, palette, typo, mood) avec 3 directions à choix | Agence | 8h itérations | 6 000-15 000€ |
| Mois 4-5 | Production des déclinaisons (print, RS, emails, animations, sons éventuels) | Agence | 8h | 4 000-12 000€ |
| Mois 5-6 | Brand guidelines complet (charte 40-80 pages) | Agence | 4h | 2 000-6 000€ |
| Mois 6 | Migration de tout l'écosystème vers la nouvelle identité | Soi-même + dev | 60h | 0€ |
| Mois 6 | INPI + protection juridique | Avocat + INPI | 4h | 600-1500€ |
| **TOTAL** | | | **~110h** | **~15 600-42 500€** |

**Avantages** : qualité maximale, identité « brand asset » solide pour levée de fonds / essaimage / vente.
**Inconvénients** : coût élevé, durée longue, risque de sur-engineering pour la taille actuelle de la communauté.
**Verdict** : **prématuré aujourd'hui**, à envisager dans 18-24 mois si essaimage national ou levée de fonds significative.

---

## 7 · Recommandation finale

### 7.1 — Action immédiate (juin-juillet 2026) — coût 0€

> **Stopper la dérive avant qu'elle ne devienne ingérable.**

1. ✅ **Trancher l'orthographe du nom** et l'appliquer partout (recherche-remplace global)
2. ✅ **Vérifier en prod** que « Nunito Rounded » se charge ; corriger si fallback silencieux
3. ✅ **Reconstruire le template email** canonique avec Inter (industrialisé dans le code)
4. ✅ **Corriger les hex du SVG logo** pour matcher les tokens CSS
5. ✅ **Aligner les gradients hero** entre app et landing
6. ✅ **Décider** : on garde ou on retire Space Grotesk de la landing ?

**Effort** : ~25h sur 4-6 semaines. Tout est faisable par le porteur seul.

### 7.2 — Action moyen terme (été-automne 2026) — scénario B recommandé

> **Combler les lacunes structurelles** sans réinventer l'existant.

1. 🎨 **Commander un set de 6-8 illustrations** vectorielles à un freelance (états vides app + onboarding + landing). Budget 600-1500€.
2. 🖨️ **Commander un kit print** (flyer A6 + affiche A3 + carte de visite). Budget 800-1500€.
3. 📱 **Commander un kit RS** Figma (10 templates multi-formats). Budget 400-800€.
4. 📄 **Déposer la marque à l'INPI** (classes 35, 38, 41, 42 selon usage). Coût ~250€.
5. 📖 **Documenter** toutes les nouvelles productions dans ce dossier.

**Effort interne** : ~30h sur 3-4 mois. **Coût externe** : ~2 000-4 000€.

### 7.3 — Action long terme (2027-2028) — selon évolution

> **Solidifier l'identité** quand la communauté atteint l'échelle.

- Si essaimage prévu / levée de fonds : envisager le **scénario C** (refonte agence) à 24-36 mois.
- Si stabilité locale : se contenter d'itérations annuelles sur les illustrations + nouveaux formats RS au fil des trends.
- Surveiller si le **logo monogramme** continue de bien fonctionner ou s'il est temps de le faire évoluer (Direction 1 ou 2 vues en 5.3).

---

## 8 · Ce que ce dossier devrait recevoir comme suite

Pour rendre l'identité visuelle vraiment **opérationnelle**, il manque encore :

- [ ] Un **mood board** photographique (10-20 références d'identités voisines admirées avec leurs URLs)
- [ ] Un **kit de fichiers source** Figma centralisé (le `tempspourtemps-design-system.fig` qui n'existe pas encore)
- [ ] Un **glossaire visuel** des catégories de services (mapping picto Lucide ↔ catégorie BDD)
- [ ] Une **galerie photo communauté** (30-50 photos validées et triées sur 12 mois d'usage)
- [ ] Une **bibliothèque audio** légère pour vidéos (jingles, fonds sonores ESS)
- [ ] Un **plan de communication annuel** lié aux saisons / temps forts (calendrier visuel)

Ces sujets sont mentionnés pour ouvrir des chantiers, **pas pour les démarrer immédiatement**.

---

## Historique

| Date | Modification |
|---|---|
| 2026-06-10 | Création initiale, audit complet, benchmark, 3 scénarios chiffrés, recommandation finale scénario B |
