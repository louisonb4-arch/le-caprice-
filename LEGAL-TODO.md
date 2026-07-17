# LEGAL-TODO — Le Caprice

Ce qui reste à obtenir, vérifier ou trancher avant que le site parte en ligne.
Tout ce qui est marqué `[à fournir]` sur les pages est en surbrillance rose : un
trou doit se voir, pas se combler avec une supposition.

**Aucune donnée n'a été inventée.** Ce qui n'a pas pu être vérifié à une source
officielle est signalé comme tel, sur la page et ici.

---

## 1. Bloquant avant la mise en ligne

### 1.1 À réclamer au client

| Donnée | Où | Pourquoi |
|---|---|---|
| **Capital social** | `mentions-legales.html` § 01 | Obligatoire dans les mentions légales d'une société commerciale. Ne figure pas au registre national. |
| **E-mail de contact** | `mentions-legales.html` § 01, § 10, § 11 · `confidentialite.html` § 01 | Un moyen de contact direct est exigé (art. 6 III-1 LCEN). Le téléphone seul ne suffit pas. |
| **Directeur de la publication** | `mentions-legales.html` § 02 | Doit être **nommé**. Pour une SAS c'est le président (Maxime Moreau) sauf désignation d'une autre personne. La société a aussi une directrice générale (Vanessa Moreau) : il faut trancher entre les deux. Nous ne le faisons pas à leur place. |
| **Hébergeur** — nom, raison sociale, adresse, téléphone, site | `mentions-legales.html` § 03 · `confidentialite.html` § 04 | Obligatoire (art. 6 III-1 LCEN). Doit nommer l'hébergeur **réellement** utilisé. |
| **Auteur des photographies** + étendue de la cession (support, durée, territoire) | `mentions-legales.html` § 05 | **Aucun crédit photo nulle part sur le site.** Si un photographe les a prises, il doit être crédité et la cession écrite. Risque de contrefaçon sinon. |
| **Durée de conservation des journaux** + transferts hors UE | `confidentialite.html` § 04 | Dépend de l'hébergeur retenu. |

### 1.2 À vérifier sur pièce

| Point | Statut | Action |
|---|---|---|
| **RCS** | `[à confirmer — RCS La Roche-sur-Yon 850 145 434]` | Le registre national ne certifie pas la ville d'immatriculation. Le greffe compétent pour la Vendée est **La Roche-sur-Yon** (et **pas** Nantes). À relire sur un **extrait Kbis**. |
| **SIRET de l'établissement** `850 145 434 00021` | Affiché | Provient du champ `alerte` de la fiche société, pas du tableau `etablissements` du registre (qui est revenu **vide**). À confirmer sur le Kbis en même temps que le RCS. |
| **Dépôt de marque « Le Caprice »** | `[dépôt de marque à confirmer]` | L'existence et le titulaire d'un éventuel dépôt INPI n'ont pas été vérifiés. |
| **Médiateur de la consommation** | `[à trancher avec le comptable]` | Art. L612-1 code de la consommation. Vise l'activité du restaurant, pas le site. Si un médiateur est déjà désigné, ses coordonnées doivent figurer en § 09. |
| **Licence GSAP** | `[licence GSAP à confirmer selon l'usage commercial]` | GSAP 3.12.5 est servi depuis le site. La licence GreenSock « Standard / No Charge » couvre a priori un site vitrine de restaurant, mais l'usage commercial mérite d'être confirmé. Lenis est en MIT, sans réserve. |

### 1.3 Maquettes de travail encore dans le dossier

`_v1-heure-doree.html` et `_v2-du-matin-a-minuit.html` sont des **versions
abandonnées** de la direction artistique. Elles ne sont pas le site, et elles
**chargent encore les polices depuis `fonts.googleapis.com`** (fuite d'IP vers
Google sans consentement). Elles contiennent aussi des cartes et des prix
périmés, ainsi qu'un lien Google Maps qui n'existe plus sur le site réel.

- `_v1-heure-doree.html` est déjà dans `.gitignore` — jamais déployé.
- **`_v2-du-matin-a-minuit.html` est suivi par git** : sans intervention, il
  serait publié et accessible en ligne.

Un fichier **`.vercelignore`** a été ajouté pour que ni l'une ni l'autre ne soit
déployée. **Action recommandée** : sortir `_v2-du-matin-a-minuit.html` du dépôt
(`git rm --cached`) ou les archiver hors du dossier du site. Elles n'ont pas été
modifiées ni supprimées — ce sont des fichiers de travail, ce n'est pas à nous
d'en décider.

### 1.4 Pas de nom de domaine, donc pas de sitemap

Le site n'a **aucun `<link rel="canonical">`, aucune balise `og:url`, aucun
`sitemap.xml`** — et le domaine définitif n'est pas arrêté. Le sitemap n'a donc
**pas** été créé : il exige des URL absolues, et le domaine aurait dû être
inventé. À faire une fois le domaine connu :

- créer `sitemap.xml` avec `index.html` (1.0), `carte.html` (0.8),
  `mentions-legales.html` (**0.2**), `confidentialite.html` (**0.2**),
  `lastmod` = date de mise en ligne ;
- ajouter les `canonical` et les `og:url` sur les quatre pages ;
- ajouter un `robots.txt` pointant le sitemap.

---

## 2. Ce qui a été vérifié

### 2.1 Identité de la société — relevé du **17 juillet 2026**

Source : registre national des entreprises, via l'API publique
`recherche-entreprises.api.gouv.fr`.

| Champ | Valeur |
|---|---|
| Dénomination sociale | **ASMV** |
| Enseigne de l'établissement | **Le Caprice** |
| Forme juridique | Société par actions simplifiée (SAS) — code 5710 |
| Siège social | 36 avenue d'Orouet, 85160 Saint-Jean-de-Monts |
| Établissement (le bar) | 195 esplanade de la Mer, 85160 Saint-Jean-de-Monts |
| SIREN | 850 145 434 |
| SIRET (siège) | 850 145 434 00013 |
| SIRET (établissement) | 850 145 434 00021 — *cf. § 1.2* |
| TVA | FR85 850 145 434 |
| APE | 56.10A — Restauration traditionnelle |
| Immatriculation | 5 avril 2019 |
| Président | Maxime Moreau |
| Directrice générale | Vanessa Moreau (née Barrault) |
| État | Actif |

**Trois pièges, traités explicitement sur la page :**

1. **« Le Caprice » n'est pas la société.** C'est l'enseigne de l'établissement.
   L'éditeur du site est **ASMV**. Le footer disait « © 2026 LE CAPRICE — TOUS
   DROITS RÉSERVÉS » : il dit maintenant « © 2026 LE CAPRICE — ASMV ».
2. **Deux adresses, et ce n'est pas une erreur.** Le siège (36 avenue d'Orouet)
   n'est **pas** l'adresse du bar (195 esplanade de la Mer). Les deux sont
   indiquées, avec l'explication.
3. **Le greffe est La Roche-sur-Yon**, pas Nantes. Le RCS reste `[à confirmer]`.

Le numéro de téléphone (09 51 06 02 89) est celui affiché par la maison sur son
propre site — pas une donnée du registre.

### 2.2 Cookies et traceurs — le constat réel

Recherche sur le code des pages publiées (`index.html`, `carte.html`,
`mentions-legales.html`, `confidentialite.html`) des motifs `cookie`,
`localStorage`, `sessionStorage`, `gtag`, `analytics`, `fbq`, `<iframe>`,
`<form>` : **aucune occurrence**.

Relevé des ressources chargées automatiquement (`<link>`, `<script>`, `<img>`,
`<iframe>`, `<source>`) pointant vers un hôte externe : **aucune**.
Aucun `@import` ni `url()` externe dans le CSS.

**Conclusion : zéro cookie, zéro requête tierce.** Donc **pas de bannière de
consentement** — art. 82 de la loi Informatique et Libertés : rien n'est déposé,
il n'y a rien à consentir. C'est un choix argumenté sur la page, pas un oubli.

Les seules URL externes restantes sont des **liens sortants** `<a href>` :
Instagram, Facebook, Tripadvisor, et (sur les pages légales) CNIL, SIL, Vokum,
`recherche-entreprises.api.gouv.fr`. Rien n'est chargé tant que l'utilisateur ne
clique pas.

### 2.3 Ce qui a été rapatrié pour obtenir ce résultat

Avant intervention, **chaque visite envoyait l'adresse IP du visiteur à Google
et à jsDelivr, sans consentement** :

| Ressource | Avant | Après |
|---|---|---|
| Archivo, Cormorant Garamond, Space Mono | `fonts.googleapis.com` + `fonts.gstatic.com` | `assets/font/*.woff2` (192 Ko) |
| GSAP 3.12.5 + ScrollTrigger | `cdn.jsdelivr.net` | `assets/js/` (113 Ko) |
| Lenis 1.1.14 | `cdn.jsdelivr.net` | `assets/js/` (13 Ko) |

Détail des polices — **SIL Open Font License 1.1**, sous-ensembles `latin` et
`latin-ext` uniquement :

- **Archivo** — variable, axe `wght` 100→900, 2 fichiers (67 Ko)
- **Cormorant Garamond** — variable **italique**, axe `wght` 300→700, 2 fichiers (74 Ko)
- **Space Mono** — statique, 400 et 700, 4 fichiers (39 Ko)

Une règle `@font-face` par famille/style/sous-ensemble, `font-display: swap`,
plages de graisse relevées dans les fichiers avec fontTools. Les bannières de
licence d'origine des fichiers JS ont été conservées.

> **Économie au passage** : la variante **droite** de Cormorant Garamond était
> chargée alors que la police n'est utilisée **qu'en italique** sur tout le site
> (13 règles CSS, toutes en `font-style:italic`). Elle n'a pas été embarquée :
> **−70 Ko**. Les 24 fichiers statiques qu'appelait l'ancienne URL Google sont
> par ailleurs devenus 8 fichiers variables.

---

## 3. Pages créées

| Fichier | Contenu |
|---|---|
| `mentions-legales.html` | Éditeur · provenance des données · directeur de la publication · hébergement · conception · propriété intellectuelle (photos, polices, bibliothèques, marques) · ce que fait le site · responsabilité · **vente d'alcool** · médiation · accessibilité · droit applicable · nous écrire |
| `confidentialite.html` | Responsable · quelles données (aucune) · **`#cookies`** · journaux de l'hébergeur · liens sortants · si vous nous écrivez · CNIL · modification |
| `assets/legal.css` | DA « Heure Dorée » appliquée aux pages légales — rubrique **« Le contre-jour »** |
| `assets/font/fonts.css` | Les `@font-face` auto-hébergées, partagées par les quatre pages |
| `.vercelignore` | Empêche le déploiement des maquettes `_v1` / `_v2` |

### Pages volontairement non créées

- **CGV** — le site ne vend rien en ligne, n'encaisse aucun paiement, n'a aucun
  formulaire. La réservation se fait **au téléphone uniquement** (« PAS DE
  RÉSERVATION EN LIGNE — UN COUP DE FIL SUFFIT »). Aucun contrat n'est conclu par
  l'intermédiaire du site : une CGV serait un document sans objet.
  Aucune CGV n'a été trouvée sur un site existant du client. **Si la maison en a
  déjà ailleurs, nous prévenir** — il faudra les lier, pas les réécrire.
- **CGU** — même raison : pas de compte, pas de service en ligne.
- **Bannière cookies** — aucun cookie déposé (§ 2.2). Rien à consentir.

---

## 4. Anomalies trouvées dans le site existant

Signalées, **non corrigées** : c'est du contenu éditorial, pas notre décision.

1. **Contradiction de saison.** `index.html` affiche « / SAISON 2025 » sur la
   carte, alors que `carte.html` affiche « SAISON 2026 — HUIT CHAPITRES » et que
   la légende de la photo d'intro dit « ÉTÉ 2026 ». L'un des deux est faux.
   Une carte datée d'une saison périmée en ligne, avec des prix, est une source
   de litige client. **À trancher.**
2. **Aucun crédit photographique**, nulle part (cf. § 1.1).
3. **Les prix sont publiés** (carte complète, 8 chapitres). La page mentions
   légales précise désormais qu'ils sont indicatifs et que seuls ceux affichés
   dans l'établissement font foi. Ça ne dispense pas de les tenir à jour.
4. **Les avis Tripadvisor sont recopiés en dur** dans `index.html` (note 4,2/5,
   179 avis, trois citations nommées). C'est licite au titre de la citation, et
   c'est mieux qu'un widget (aucun traceur). Mais **la note et le nombre d'avis
   se périment** : ils devront être revus, ou présentés avec leur date de relevé.
5. Le dossier `../lecaprice-site-assets` existe à côté du site. Non consulté, non
   modifié.

---

## 5. À vérifier après la mise en ligne

- [ ] Les deux pages répondent en **200** sur le domaine réel.
- [ ] `confidentialite.html#cookies` scrolle bien à la section Cookies.
- [ ] Console navigateur : `document.cookie` renvoie une chaîne vide.
- [ ] Onglet Réseau : **aucune** requête vers un domaine autre que celui du site
      (en particulier ni `fonts.gstatic.com` ni `cdn.jsdelivr.net`).
- [ ] Les liens du footer fonctionnent depuis les **quatre** pages.
- [ ] `_v1-heure-doree.html` et `_v2-du-matin-a-minuit.html` ne sont **pas**
      accessibles en ligne.
- [ ] Le bloc hébergeur est rempli — sinon les mentions sont incomplètes.
- [ ] Aucun `[à fournir]` rose ne subsiste sur les pages publiées.

---

*Pages légales et rapatriement des polices : Vokum — 17 juillet 2026.*
