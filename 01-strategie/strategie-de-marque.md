# 01 · Stratégie de marque

> **Étape 1 du framework identité visuelle** (cf. support de formation « framework identité visuelle » — document tiers non versionné).
> Ce document est la **fondation** : tout le reste (logo, couleurs, typo, univers visuel) doit en découler.

[← Retour au sommaire](../README.md)

---

## 1.1 — Nom & promesse

| | |
|---|---|
| **Nom officiel** | TempsPourTemps |
| **Acronyme** | TpT |
| **Wordmark** | écrit `TempsPourTemps` (sans espace, casse mixte) dans les emails — incohérence à arbitrer, voir [audit 07](../07-audit-critique/audit-critique-roadmap.md) |
| **Promesse principale** | « Échangez du temps, pas de l'argent » |
| **Territoire actuel** | Saint-Sébastien-sur-Loire (banlieue de Nantes) — vocation à essaimer |

---

## 1.2 — Mission

> **Reconnecter le voisinage par l'entraide concrète.**

Deux dimensions co-existent et doivent s'exprimer **simultanément** dans tous les choix visuels :

1. **Lien humain** — recréer du tissu social, sortir de l'isolement, faire des rencontres locales
2. **Service utile** — le coup de main quotidien, le dépannage entre voisins, l'utilité immédiate

⚠️ **Tension à gérer** : ces deux dimensions tirent dans des directions visuelles différentes.
- Le « lien humain » pousse vers le chaleureux, le rond, l'illustratif, l'émotionnel.
- Le « service utile » pousse vers la clarté, la lisibilité, le fonctionnel, le rassurant.

→ **Arbitrage de marque** : la chaleur sert l'utilité. On ne sacrifie ni la clarté ni la chaleur.

---

## 1.3 — Valeurs (les 3 piliers visuels)

Hiérarchie de priorité pour les décisions visuelles :

### 🌿 1. Chaleur / convivialité
> Une marque qu'on a envie d'inviter à dîner.

- **Couleurs chaudes** dominantes (sable, orange brûlée)
- **Formes arrondies** (Nunito Rounded, radius généreux 1.5rem sur les cards)
- **Ton** accueillant, tutoiement, langage simple

### 🛡️ 2. Confiance / sérieux
> Une marque qui ne disparaîtra pas dans 6 mois et à qui on confie ses heures.

- **Ancrage marine** (#183e57) qui contrebalance les couleurs chaudes
- **Typographie nette** pour le corps de texte (Inter)
- **Constance** : ne pas changer d'identité tous les 6 mois (cf. conseils PDF)

### ✨ 3. Simplicité / accessibilité
> Une marque qu'une personne de 15 ans comme de 75 ans comprend immédiatement.

- **Pas de jargon graphique** (pas de dégradés acidulés, pas d'effets décoratifs gratuits)
- **Pictogrammes géométriques** clairs, pas d'illustration ambiguë
- **Contraste fort** (WCAG AA minimum, AAA visé sur les titres)

---

## 1.4 — Cible

### Persona principal : la communauté intergénérationnelle de Saint-Sébastien

L'identité visuelle ne s'adresse **pas** à une tranche d'âge unique. Elle doit **parler simultanément** à :

| Groupe | Attentes visuelles |
|---|---|
| **Familles 30-55 ans** | Praticité, mobile-first, lisibilité, codes contemporains (radius arrondi, micro-interactions) |
| **Seniors 55-75 ans** | Lisibilité (typo min 16px), contraste élevé, codes rassurants (pas trop « startup »), navigation prévisible |
| **Néo-arrivants 25-40 ans** | Codes contemporains, identité forte et différenciante, sens du collectif assumé |
| **Adolescents / jeunes adultes** | Pas la cible primaire mais ne doit pas créer de répulsion |

### Implications visuelles
- **Police corps min 16px** sur mobile (déjà appliqué dans `main.css` ligne 384)
- **Contraste AA minimum** sur tous les textes
- **Pas de hover-only** pour des informations critiques (les utilisateurs tactiles n'ont pas de hover)
- **Vocabulaire visuel intemporel** plutôt que « tendance 2026 » qui sera daté en 2028

---

## 1.5 — Personnalité (le « si TpT était une personne »)

### Profil double validé
1. **Voisin·e bienveillant·e** — accueillant, simple, sourit facilement, pas guindé, parle à tout le monde
2. **Animateur·rice de quartier** — énergique, fédérateur, propose toujours quelque chose, met en lien

### Traits à incarner visuellement
- ✅ **Chaleureux sans être mièvre** (pas de cœurs ni de pastels acidulés)
- ✅ **Pragmatique sans être froid** (pas de monochrome, pas de minimalisme silicon-valley)
- ✅ **Énergique sans être agressif** (pas de rouge vif, pas de typos lourdes condensées)
- ✅ **Local sans être folklorique** (pas de codes régionalistes appuyés)

### Traits à éviter
- ❌ Trop « institutionnel/mairie » (typos serif lourdes, mises en page rigides)
- ❌ Trop « startup tech » (gradients néon, typos ultra-condensées, pictos abstraits)
- ❌ Trop « asso militante » (visuels engagés au point d'exclure)
- ❌ Trop « senior-friendly » caricatural (très grosses polices, beige unique, aucune modernité)

---

## 1.6 — Ton & langage (en complément du visuel)

Même si ce dossier traite de l'identité **visuelle**, ces règles influencent les compositions :

- **Tutoiement** systématique dans l'app, vouvoiement possible en email institutionnel
- **Français simple**, pas d'anglicismes inutiles (« annonce » > « post », « rendez-vous » > « booking »)
- **Phrases courtes** dans les CTA (« Proposer un coup de main », « Voir l'échange »)
- **Émojis avec parcimonie** : OK en emails communautaires (cf. 🎉 dans l'email du 17 juin), à proscrire dans l'UI de l'app et dans les communications institutionnelles

---

## 1.7 — Positionnement vs concurrents

Voir aussi le **benchmark concurrentiel détaillé** dans [07 · Audit](../07-audit-critique/audit-critique-roadmap.md#benchmark-concurrentiel).

| Acteur | Codes visuels typiques | Notre différenciation |
|---|---|---|
| **Accorderie** (réseau Quebec/France) | Vert/orange, sérieux institutionnel, codes assos | Plus moderne, plus chaleureux, plus app-first |
| **SEL** (Systèmes d'Échange Local) | Codes années 90/2000, peu d'identité visuelle unifiée | Identité contemporaine et cohérente |
| **Time Republik** (international) | Très tech/SaaS, anglais, froid | Local, chaleureux, humain, français |
| **Indy / KissKissBankBank** (économie alternative) | Codes startup colorés | Plus posé, plus voisinage |
| **Allo-Voisins / Mes-Allocs** (services voisinage) | Très marketing/commercial | Non-marchand assumé, communautaire |

### Notre niche visuelle
> Une **app moderne** (codes 2026, mobile-first, micro-interactions) habillée d'**une chaleur de quartier** (palette ocre/sable, typo arrondie, vocabulaire familier), qui inspire **confiance par la sobriété** (marine ancrant, pas de surcharge).

---

## 1.8 — Décisions stratégiques à prendre (et leur deadline)

Voir le détail dans [07 · Audit](../07-audit-critique/audit-critique-roadmap.md), résumé ici :

| Décision | Échéance suggérée | Coût/Impact |
|---|---|---|
| Choisir le nom canonique (« TempsPourTemps » vs « TempsPourTemps ») | Avant essaimage hors St-Sébastien | Faible |
| Trancher : 2 typos (app) ou 3 typos (landing) ? | Avant prochain audit doc | Faible |
| Faire un logo « pro » (vs le monogramme actuel) ? | Avant levée de fonds / dépôt marque | 500€-5000€ freelance |
| Déposer la marque à l'INPI | Avant essaimage ou couverture presse | ~250€ + suivi |

---

## Historique

| Date | Modification |
|---|---|
| 2026-06-10 | Création initiale à partir du cadrage utilisateur (10 questions) |
