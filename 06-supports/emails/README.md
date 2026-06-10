# 06.1 · Template email canonique

> **Extrait et formalisé** à partir de `exemple-email-cloture-17juin.html` (notre meilleur template actuel — généré par itérations IA, pas par un vrai éditeur d'email).
> Ce document définit la **structure canonique** à respecter pour tout nouvel email, **en attendant** une reconstruction propre (cf. recommandation dans l'audit).

[← Retour aux supports](../declinaisons-supports.md) · [← Sommaire](../../README.md)

---

## ⚠️ Avertissement préalable

Le template actuel a deux défauts majeurs :

1. **Il utilise Georgia (serif)** pour tout le contenu → **incohérent** avec le design system (Nunito Rounded + Inter). Voir l'arbitrage à faire dans [04 · Typographie, § 4.6](../../04-typographie/typographie.md#46--cas-particulier--les-emails).
2. **Il n'est pas industrialisé** : c'est un fichier HTML créé à la main, copié-collé/édité à chaque envoi. **Aucune version dans le code de l'app**. Les emails transactionnels (notifs, digests) utilisent d'autres templates inline qui ne suivent pas cette structure.

→ **Recommandation** : utiliser ce template comme **base de design**, mais réécrire les helpers `server/utils/brevo*.ts` pour produire ces emails **depuis du code** (template engine type Handlebars/MJML).

---

## Structure canonique en 7 blocs

```
┌───────────────────────────────────────┐
│  1. WRAPPER (fond blanc, padding)     │
│   ┌─────────────────────────────┐     │
│   │  2. HEADER (marine + sable) │     │  ← eyebrow + titre
│   ├─────────────────────────────┤     │
│   │  3. BANNER DATE (sable)     │     │  ← événementiel uniquement
│   ├─────────────────────────────┤     │
│   │  4. BODY (crème)            │     │
│   │   ┌─ Paragraphes ─┐         │     │
│   │   ├─ BLOCK info ──┤         │     │  ← border-left coloré
│   │   ├─ Paragraphes ─┤         │     │
│   │   └─ CTA bouton ──┘         │     │
│   ├─────────────────────────────┤     │
│   │  5. FOOTER (marine + sable) │     │  ← signature
│   ├─────────────────────────────┤     │
│   │  6. MENTIONS (gris discret) │     │  ← légales, désinscription
│   └─────────────────────────────┘     │
│  7. WHITESPACE EXTÉRIEUR              │
└───────────────────────────────────────┘
```

---

## Code de référence (à adapter)

> Polices : pour cohérence avec design system, remplacer `'Georgia', serif` par `Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif` partout (sauf le titre H1 qui peut utiliser un fallback équivalent Nunito Rounded en local).

### 1. Wrapper externe

```html
<table width="100%" cellpadding="0" cellspacing="0"
       style="background-color:#ffffff; padding:20px 12px;">
  <tr>
    <td align="center">
      <table cellpadding="0" cellspacing="0"
             style="max-width:560px; width:100%;
                    border-radius:12px; overflow:hidden;">
        <!-- BLOCS 2 à 6 ici -->
      </table>
    </td>
  </tr>
</table>
```

### 2. Header (marine + texte sable)

```html
<tr>
  <td style="background-color:#183e57;
             padding:28px 24px 24px;
             border-radius:12px 12px 0 0;">

    <p style="margin:0 0 6px;
              font-size:11px;
              color:#fcdb81;
              letter-spacing:0.12em;
              text-transform:uppercase;
              font-family: Inter, sans-serif;">
      TempsPourTemps
    </p>

    <h1 style="margin:0;
               font-size:28px;
               font-weight:normal;
               color:#fcdb81;
               line-height:1.2;
               font-family: 'Nunito Rounded', Inter, sans-serif;">
      Titre de l'email — accroche courte
    </h1>
  </td>
</tr>
```

### 3. Banner date (sable plein) — optionnel, événementiel

```html
<tr>
  <td style="background-color:#fcdb81; padding:16px 24px;">
    <p style="margin:0;
              font-size:18px;
              color:#183e57;
              font-weight:bold;
              font-family: Inter, sans-serif;">
      Mercredi 17 juin · à partir de 17h30
    </p>
    <p style="margin:4px 0 0;
              font-size:13px;
              color:#183e57;
              opacity:0.7;
              font-family: Inter, sans-serif;">
      Saint-Sébastien-sur-Loire
    </p>
  </td>
</tr>
```

### 4. Body principal (fond crème, paragraphes)

```html
<tr>
  <td style="background-color:#f5f0e8; padding:28px 24px;
             font-family: Inter, sans-serif;">

    <p style="margin:0 0 18px;
              font-size:16px;
              color:#1a1a1a;
              line-height:1.7;">
      Salut,
    </p>

    <p style="margin:0 0 18px;
              font-size:16px;
              color:#1a1a1a;
              line-height:1.7;">
      Texte principal du message…
    </p>

  </td>
</tr>
```

### 4.b — Block info (border-left coloré)

> 2 variantes :
> - Border-left **sable** `#fcdb81` → info principale, événementielle
> - Border-left **marine** `#183e57` → info secondaire, contextuelle

```html
<table width="100%" cellpadding="0" cellspacing="0" style="margin-bottom:22px;">
  <tr>
    <td style="border-left:4px solid #fcdb81;
               background-color:#fdf6e3;
               border-radius:0 10px 10px 0;
               padding:16px 18px;">

      <p style="margin:0 0 6px;
                font-size:11px;
                color:#183e57;
                letter-spacing:0.1em;
                text-transform:uppercase;
                font-weight:bold;
                font-family: Inter, sans-serif;">
        📍 Où
      </p>

      <p style="margin:0;
                font-size:15px;
                color:#1a1a1a;
                line-height:1.6;
                font-family: Inter, sans-serif;">
        Jardin et studio d'artiste d'Andrée<br>
        161 rue de la Libération, Saint-Sébastien-sur-Loire.
      </p>
    </td>
  </tr>
</table>
```

### 4.c — CTA bouton (à ajouter, manquant dans l'exemple)

```html
<table cellpadding="0" cellspacing="0" style="margin:24px 0;">
  <tr>
    <td align="center"
        style="background-color:#183e57;
               border-radius:9999px;
               padding:14px 28px;">
      <a href="{{URL_CTA}}"
         style="color:#fcdb81;
                text-decoration:none;
                font-size:16px;
                font-weight:bold;
                font-family: Inter, sans-serif;">
        Confirmer ma présence
      </a>
    </td>
  </tr>
</table>
```

### 5. Footer (marine + sable, signature)

```html
<tr>
  <td style="background-color:#183e57;
             padding:22px 24px;
             border-radius:0 0 12px 12px;
             font-family: Inter, sans-serif;">
    <p style="margin:0 0 4px;
              font-size:15px;
              color:#fcdb81;">
      À très vite,
    </p>
    <p style="margin:0;
              font-size:15px;
              color:#fcdb81;
              font-weight:bold;">
      Omar-Yann, Karine et Mathilde
    </p>
  </td>
</tr>
```

### 6. Mentions légales (à ajouter, manquant dans l'exemple)

```html
<tr>
  <td style="padding:16px 24px 0;
             font-family: Inter, sans-serif;">
    <p style="margin:0;
              font-size:11px;
              color:#717182;
              line-height:1.5;
              text-align:center;">
      Vous recevez cet email parce que vous êtes inscrit·e à Temps pour Temps.<br>
      <a href="{{URL_PREFS}}"
         style="color:#717182; text-decoration:underline;">
        Gérer vos préférences
      </a>
      ·
      <a href="{{URL_UNSUB}}"
         style="color:#717182; text-decoration:underline;">
        Se désabonner
      </a>
    </p>
  </td>
</tr>
```

---

## Variables / placeholders à standardiser

Pour faciliter une future industrialisation (passage en template engine) :

| Placeholder | Sens | Exemple |
|---|---|---|
| `{{FIRST_NAME}}` | Prénom du destinataire | `Marie` |
| `{{EYEBROW}}` | Suréligne header | `TempsPourTemps` (default), `Newsletter`, `Notification` |
| `{{TITLE}}` | H1 principal | `Fin de la phase expérimentale` |
| `{{HAS_BANNER}}` | Booléen affichage banner | `true` |
| `{{BANNER_TITLE}}` | Texte de la banner | `Mercredi 17 juin · 17h30` |
| `{{BANNER_SUBTITLE}}` | Sous-texte banner | `Saint-Sébastien-sur-Loire` |
| `{{BODY_BLOCKS[]}}` | Liste de blocs (paragraphes, infoblocks, CTA) | — |
| `{{SIGNATURE_LINE_1}}` | « À très vite, » | — |
| `{{SIGNATURE_LINE_2}}` | « Omar-Yann, Karine et Mathilde » | — |
| `{{URL_PREFS}}` | Lien gestion préférences | `https://app.../profile/preferences` |
| `{{URL_UNSUB}}` | Lien désinscription | `https://app.../unsub/{{TOKEN}}` |

---

## Compatibilité clients email

Testé/compatible :
- ✅ Gmail web + mobile
- ✅ Apple Mail (macOS, iOS)
- ⚠️ Outlook desktop (vérifier le rendu des border-radius, peuvent être ignorés)
- ⚠️ Outlook web (idem)
- ✅ Yahoo Mail
- ✅ ProtonMail

### Précautions HTML email
- ❌ Pas de Flexbox / Grid (utiliser des `<table>`)
- ❌ Pas de CSS externe / `<style>` complexes (tout inline)
- ❌ Pas de `position: absolute`
- ⚠️ Border-radius support partiel sur Outlook
- ✅ Toutes les couleurs en hex (pas de noms de couleurs)
- ✅ `font-family` inline sur **chaque** élément texte (pas d'héritage fiable)
- ✅ Tailles en `px` (pas de `rem`, `em`)
- ✅ Liens : `target="_blank"` + `rel="noopener"`

### Tests recommandés
- **Litmus** (payant) ou **Mailtrap** (freemium) pour preview multi-clients
- Envoi de tests à 3-4 adresses différentes (Gmail, Outlook, iCloud) avant déploiement
- Tester la version texte brut (fallback que certains clients utilisent)

---

## Variantes par type d'email

### Type 1 — Email transactionnel
Confirmation, RDV planifié, notif de réservation.
- Header simple, pas de banner
- Body court (1-3 paragraphes)
- 1 CTA principal
- Footer signature équipe possible mais facultatif
- **Doit absolument** avoir un lien de désabonnement et mentions

### Type 2 — Email événementiel
Annonce événement, apéro, AG.
- Header avec accroche émotionnelle
- **Banner date** obligatoire
- Body 3-5 paragraphes + 1-2 infoblocks
- CTA confirmation présence
- Footer signature équipe

### Type 3 — Newsletter / Digest
Récap d'activité, chiffres-clés communautaires.
- Header avec image de couverture optionnelle
- Pas de banner date
- Body structuré en sections claires (titres niveau 2)
- Liens vers contenus app
- Footer + mentions

### Type 4 — Email administratif
Reset password, suppression compte, RGPD.
- Header sobre, sans émoji
- **Pas de banner**
- Body minimal, instructions claires
- CTA unique
- Mentions complètes
- **Aucune** signature personnelle (institutionnel)

---

## Historique

| Date | Modification |
|---|---|
| 2026-06-10 | Extraction depuis l'email du 17 juin, formalisation du template canonique, identification des manques (CTA, mentions, variantes) |
