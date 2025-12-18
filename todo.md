## Next

### hero section

Là où j'en suis.

#### Front matter

```toml
[hero]
  enabled = true
  variant = "split"
  image = "montagne_vercors.jpg"
  theme = "light"
  size = "md"
  overlay = false
```

Pour l'instant juste `enabled` est mis en place, ça déclenche une condition
positive dans baseof et ça importe `partials/ui/hero.html`

Dans la partial, ça récupère le `.RawContent` qu'il y a jusqu'au premier `h2`.

Ça récupère l'image suggérait par le front matter et la met dans un div
approprié.

Ensuite le contenu est affiché.

Le problème de laisser l'image dans le front matter, c'est que ça bypass tout
mon module d'optimisation des images.

J'ai pris des notes dans `perso/sci/site/hero` et il y avait une proposition de
design par chatgpt ici :
https://chatgpt.com/s/t_694408fd47c08191b8de0fcd1d0ef311

**TODO** :

- voir si on peut sortir l'image du front matter. Elle pourrait tout simplement
  être dans un shortcode `{{< hero img />}}` qui accepterait une image où une
  galerie.
- ou tout simplement dans du markdown et affiché en hero parce qu'elle est dans
  ce bloc

### form

Les deux propositions intéressantes (la première permet même d'avoir deux
formulaires différents:

- https://formspree.io/
- https://usebasin.com/pricing

### Contenu

- voir comment sont construites les sections:
  - ~~si je garde les liens de sous-pages, les mettre en bas de pages~~
- vérifier la construction des liens internes au site:
  - ~~depuis le footer~~
  - vers les pages hors-menus comme chambre
  - les CTA comme `vérifier les dispos`
- Mettre toutes les images disponibles
- Relever les images à faire et les commenter
- Relire tous les textes
- sitempap ? Quoi, comment, où ?

### Design

- garde-ton le toc ?
- si oui, je suis embetté avec ces titres à rallonges, il faudrait un système de
  `linkTitle`
- Quel menu visuel en haut
- quel logo
- est-ce que je garde la structure actuelle du site
- sortir tout le css du content (footer et boutons)
- mettre une galerie/carrousel

### Pages à créer

Pièces du lieu:

- sanitaires
- salle centrale
- filet suspendu

Attention je ne parle pas des sanitaires dans la grande page sur le gîte. Je me
demande si pour les 3 pages précédentes, des galeries photos dans la page du
gîte suffiraient.

Une rubrique vie du lieu, avec :

- historique de la construction
- le projet de studio (à bien voir si je ne me mets pas en danger
  législativement)
- historique du projet (avec l'envie de studio)
- des pages techniques sur le lieu:
  - les arbres du terrain
  - les plantes d'intérieur

## JSON-LD

- LodgingBusiness sur la page "gite", englobe:
  - adresse
  - géolocalisation
  - capacités
  - équipements
  - liens vers offres
- Offer (tarifs) sur la page "tarifs":
  - prix indicatif
  - période (week-end / semaine)
  - devise
  - lien vers contact ou réservation
- Organization imbriquée dans LodgingBusiness (sinon redondant)
- BreadcrumbList seulement sur les pages de niveau 3
- FAQPage sur la faq
- Review / AggregateRating, ou mais attention :
  - avis réels
  - source identifiable

Petit plus :

- ImageObject → utile si belles photos clés, bien nommées et bien décrites

## breadcrumb

Breadcrumb en html et json-ld.

À ne pas faire apparaître que dans les sous-pages de niveau 3

```
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Accueil",
      "item": "https://ausondudiois.fr/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Le gîte",
      "item": "https://ausondudiois.fr/gite-de-groupe-drome/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Les chambres",
      "item": "https://ausondudiois.fr/gite-de-groupe-drome/les-chambres/"
    }
  ]
}
</script>
```

Il va falloir faire un shortcode pour qu'il soit créé automatiquement.

## Les pages

Il faut faire un **footer**.

Dans les activités locales:

- [x] Vignobles & Clairettes
- [x] Baignades & Spots d'eau

Dans le site:

- [x] les chambres
- [x] FAQ et informations pratiques
- [x] Contact — Disponibilités — Conditions

Je me demande si contact est nécessaire sachant que les contacts seront dans le
footer. Disponibilités pareil, y'a "réserver".

## Microdatas

- aide les moteurs de recherche à comprendre le contenu du site
- permet d'afficher des rich snippets dans les résultats de recherche

Les microdatas doivent être affichés en html et en `JSON-LD`. Avec hugo il
faudra probablement faire un shortcode et stockés les données dans data.

https://chatgpt.com/s/t_693c2c3467a88191a4ec695135617ad4

## Structure du site

1. Accueil

- Slug: /
- H1: Gîte de groupe près de Die — Au son du Diois
- <title>: Gîte de groupe près de Die (Drôme) — Au son du Diois
- Menu (court): Accueil
- Meta description: Gîte 15 pers. en Diois — espace central lumineux, cuisine
  collective et grand terrain en lisière de forêt. Vue imprenable sur le
  Vercors. Vérifiez les disponibilités.

Hero

- Titre hero: Gîte 15 personnes • Éco-construit • Vue Vercors
- Sous-titre: Grand espace pour groupes, stages et familles — cuisine
  collective, terrasse et vaste domaine naturel.
- CTA principal: Vérifier les disponibilités (bouton)
- Image recommandée: façade-terrasse-vue-vercors.jpg (golden hour, large)
- Remarque SEO: inclure un petit texte alt & caption avec mots-clés (gîte 15
  personnes Die Vercors).

2. Hébergement / Le gîte (page détaillée)

- Slug: /le-gite
- H1: Le gîte — capacité 15 personnes
- <title>: Le gîte — Au son du Diois | Gîte 15 pers. près de Die (Vercors)
- Menu (court): Le gîte
- Meta description: Description complète du gîte Au son du Diois : grande salle
  lumineuse, matériaux en pisé, cuisine collective, chambres et équipements pour
  15 personnes.

Hero

- Titre hero: Un espace pensé pour les groupes
- Sous-titre: 100 m² d’espace central, matériaux naturels et confort pour un
  séjour collectif réussi.
- CTA: Voir la fiche technique
- Image recommandée: salle-vie-volume.jpg (intérieur grand angle montrant mur en
  pisé + hauteur)

3. Tarifs & Réservation

- Slug: /tarifs-reservation
- H1: Tarifs & réservation
- <title>: Tarifs & réservation — Gîte 15 pers. Au son du Diois | Réservez direct
- Menu (court): Tarifs
- Meta description: Grille tarifaire et conditions pour le gîte 15 personnes.
  Réservez direct pour le meilleur tarif. Minima de séjour en haute saison,
  draps fournis, arrivée autonome.

Hero

- Titre hero: Réservez votre séjour — meilleur tarif garanti
- Sous-titre: Consultez la disponibilité, les conditions et nos tarifs directs
  (sans commission plateforme).
- CTA: Vérifier le calendrier
- Image recommandée: terrasse-vue.jpg (table en extérieur, vue Vercors)

4. Le domaine & Extérieur

- Slug: /domaine-exterieur
- H1: Le domaine — terrain, terrasses & nature
- <title>: Le domaine & l'extérieur — gîte 15 pers. Au son du Diois (Die, Vercors)
- Menu (court): Domaine
- Meta description: Terrain naturel de plusieurs milliers de m² en lisière de
  forêt, terrasses, sentiers et accès proche à une rivière sauvage — idéal pour
  activités extérieures et tentes.

Hero

- Titre hero: 3 000–4 000 m² en lisière de forêt (si tu préfères ne pas
  préciser, remplacer par Vaste terrain naturel)
- Sous-titre: Terrasse en bois, sentiers, coins de nature et possibilités
  d’installation de tentes.
- CTA: Découvrir l'extérieur
- Image recommandée: terrain-sentier.jpg (panorama montrant continuité
  forêt/terrain)

5. Vie locale & Activités

- Slug: /vie-locale-activites
- H1: Vie locale & activités autour de Die
- <title>: Activités à Die et dans le Diois — randos, Drôme Aventure, marchés
- Menu (court): Vie locale
- Meta description: Infos pratiques et idées d'activités : Drôme Aventure,
  randonnées, marchés locaux, restaurants et ressources pour organiser vos
  sorties depuis le gîte.

Hero

- Titre hero: Explorez le Diois
- Sous-titre: Randonnées, activités sportives, marchés et bonnes adresses à deux
  pas du gîte.
- CTA: Voir les activités
- Image recommandée: drôme-aventure-exterieur.jpg ou rando-vue-vercors.jpg

6. FAQ & Informations pratiques

- Slug: /faq-informations-pratiques
- H1: FAQ & informations pratiques
- <title>: Infos pratiques & FAQ — Au son du Diois | Arrivée, draps, toilettes sèches
- Menu (court): Infos pratiques
- Meta description: FAQ : arrivée autonome, kit initial de draps, toilettes
  sèches, politique hors TVA, équipements et conseils pour un séjour en toute
  sérénité.

Hero

- Titre hero: Questions fréquentes & informations utiles
- Sous-titre: Arrivée, draps fournis, sanitaires, règles du gîte et
  recommandations pratiques.
- CTA: Lire la FAQ
- Image recommandée: poele-feu.jpg ou chambre.jpg (ambiance pratique)

7. Contact — Disponibilités — Conditions

- Slug: /contact-disponibilites
- H1: Contact & disponibilités
- <title>: Contact & disponibilités — Réserver le gîte Au son du Diois
- Menu (court): Contact
- Meta description: Contactez-nous pour disponibilité et réservation. Formulaire
  rapide, téléphone et lien vers calendrier. Réponse rapide sous 48h.

Hero

- Titre hero: Contactez-nous / Vérifiez les disponibilités
- Sous-titre: Formulaire simple, téléphone click-to-call et lien vers le
  calendrier de réservation.
- CTA: Demander un devis
- Image recommandée: façade-signal.jpg ou map-gite.jpg (carte + repère)

### Les chambres

Faire une page dédiée pour les chambres, je ne sais pas encore si elle sera dans
le menu principal où juste accessible depuis la page `Le gîte`.
