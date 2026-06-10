# 02 · Logo

> **Étape 2 du framework identité visuelle.** Élément central, unique, mémorable, qui doit représenter l'essence de la marque.

[← Retour au sommaire](../README.md)

---

## 2.1 — Statut actuel : **provisoire mais fonctionnel**

Le logo actuel n'est **pas considéré comme définitif** par le porteur du projet, mais il est :
- ✅ Utilisé partout (app, landing, favicon, icône PWA, OG image)
- ✅ Aligné sur le design system (marine + sable)
- ✅ Conservable sur le long terme tant qu'aucune décision contraire n'est prise

**Implication** : tout le présent document décrit le logo *actuel* (à documenter), pas un futur logo (à concevoir). Les recommandations d'évolution sont dans [07 · Audit](../07-audit-critique/audit-critique-roadmap.md).

---

## 2.2 — Description visuelle

### Forme principale
Monogramme « **tpt** » (initiales de **t**emps **p**our **t**emps) en jaune sable sur fond carré marine.

- **Lettrage** : trois caractères stylisés `t`, `p`, `t`, dessinés en formes pleines, bouts arrondis
- **Détail signature** : un **petit cercle marine** au centre du `p`, qui crée le « contre-poinçon » de la boucle. C'est ce détail qui donne sa personnalité au logo et le rend reconnaissable au format icône (16×16, 32×32).
- **Cadre** : carré plein marine, ratio 1:1 sur l'icône, parfois inscrit dans un conteneur ovale ou rectangulaire sur les autres usages
- **Aucun wordmark accolé** dans la version icône (la version texte est séparée)

### Couleurs exactes du SVG actuel
| Élément | Hex |
|---|---|
| Fond | `#28445D` |
| Lettres | `#F9DA8F` |
| Détail cercle dans le `p` | `#28445D` (même que le fond) |

⚠️ **Divergence à noter** : ces hex sont **proches mais non identiques** aux tokens du design system (`#183e57` et `#fcdb81`). Le SVG actuel a été créé avant la formalisation des tokens. À harmoniser lors d'une future revue (cf. [07 · Audit](../07-audit-critique/audit-critique-roadmap.md)).

---

## 2.3 — Variantes disponibles

Toutes dans [`../assets/logo/`](../assets/logo/) :

| Fichier | Usage | Format |
|---|---|---|
| `logo-tempspourtemps.svg` | Web, print, scaling parfait | SVG vectoriel |
| `logo-tpt-fond.png` | Quand le fond marine doit être garanti | PNG 512×512 |
| `logo-tpt-transparent.png` | Sur fonds clairs maîtrisés | PNG transparent |
| `logo-source.png` | Fichier source haute résolution | PNG haute déf |
| `icon-pwa-512.png` | Icône PWA / app stores | PNG 512×512 |
| `apple-touch-icon.png` | iOS home screen | PNG |
| `favicon.ico` | Onglet navigateur | ICO multi-tailles |

### Variantes manquantes (à produire)
- ❌ **Version monochrome noire** (pour photocopies, fax administratifs, tampons)
- ❌ **Version monochrome blanche** (pour fonds très foncés ou colorés)
- ❌ **Wordmark seul** « Temps pour Temps » en SVG, indépendant du monogramme
- ❌ **Combinaison wordmark + monogramme** en SVG (lockup horizontal et vertical)
- ❌ **Version « long format »** pour bandeaux RS (LinkedIn cover, FB header)

Ces lacunes sont listées dans la roadmap de [07 · Audit](../07-audit-critique/audit-critique-roadmap.md).

---

## 2.4 — Règles d'usage (à respecter)

### ✅ DO

- **Zone de protection** : laisser au minimum la **hauteur d'un `t`** d'espace libre autour du logo
- **Taille minimum** : 24px de côté à l'écran, 8mm en print (en deçà le cercle du `p` devient invisible)
- **Fond uni** quand possible (le sable ressort mieux sur fond crème `#f7f6f3` ou blanc que sur photos chargées)
- **Sur photo** : utiliser la version sur fond marine pour garantir le contraste

### ❌ DON'T

- ❌ Ne pas **déformer** (étirer, écraser) le logo
- ❌ Ne pas **changer les couleurs** du logo (sauf passage en monochrome maîtrisé)
- ❌ Ne pas **rajouter d'effets** (ombre portée, glow, biseau) au-delà d'une légère ombre douce sur les CTAs
- ❌ Ne pas **inverser** les couleurs (lettres marine sur fond sable) — l'identité repose sur sable-sur-marine
- ❌ Ne pas **rajouter de texte accolé** sans passer par les lockups officiels (à produire)
- ❌ Ne pas **utiliser sur fond orange brûlée** (#d65e1c) : la lisibilité du sable est mauvaise

---

## 2.5 — Concept et symbolisme

### Lecture du monogramme

- Les **3 lettres `t-p-t`** lisent le nom de la marque sans le déployer
- Le **`p` central** (avec son cercle) agit comme un **point d'équilibre**, métaphore d'**échange équitable** : ce que je donne = ce que je reçois
- Le **format carré** évoque la **stabilité, l'ancrage, la fiabilité** (vs un logo flottant ou diagonal qui suggérerait l'instabilité)
- Les **couleurs marine + sable** évoquent : marine = profondeur, confiance, sérieux ; sable = chaleur humaine, soleil, optimisme

### Ce qui ne fonctionne pas (à challenger)

À investiguer dans [07 · Audit](../07-audit-critique/audit-critique-roadmap.md) :
- Le monogramme `tpt` est **lisible mais pas immédiatement parlant** sans le contexte du nom complet
- Aucun **symbole de connexion/échange** explicite (pas de flèche, pas de cercle, pas de mains)
- Aucun **ancrage géographique** (rien ne dit « voisinage / local »)
- Reconnaissance internationale **non testée** (le `p` peut se confondre avec un `b`)

---

## 2.6 — Logo et écosystème de marque

### Co-signatures fréquentes
- **« Présenté par … »** — citoyens fondateurs (Omar-Yann, Karine, Mathilde) — utilisé dans les emails
- **Partenaires institutionnels potentiels** — Mairie de St-Sébastien, départements, Région Pays-de-la-Loire
- **Réseaux d'économie sociale** — Accorderie, SEL, etc.

### Règles de co-signature (à établir)
Aucune règle formalisée à date. À définir avant le premier dossier de partenariat / subvention.

---

## Historique

| Date | Modification |
|---|---|
| 2026-06-10 | Création initiale, inventaire des assets, repérage des variantes manquantes |
