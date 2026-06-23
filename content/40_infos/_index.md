+++
title = "Contact et Agenda"
linkTitle = "Tarifs/infos"
slug = "contact"
TOC = true
weight = 15
layout = "single"
+++

<div class="cta">
    <a href="#dispo">Disponibilités</a>
    <a href="#reserver">Réserver</a>
</div>

## Tarifs

- Nous privilégions les **séjours longs** → les tarifs sont fortement dégressifs
- Pour les **réservations de dernière minute**, contactez-nous pour un devis
  très arrangeant !
- Le tarif **inclut** :
  - Un kit de **draps** initial
  - La **taxe de séjour** (collectée puis reversée à la commune)
  - Un **ménage professionnel** (le gîte doit être laissé dans un état correct
    d’usage)

> Les tarifs affichés ici correspondent aux réservations directes. Les tarifs
> visibles sur les plateformes peuvent varier selon leurs frais, leurs règles de
> calcul et leurs commissions.

### Basse saison

Toute l’année (hors vacances d’été, week-ends prolongés et fêtes de fin d’année)


| Durée   | Total lot 2 gîtes | Prix par nuitée |
| ------- | ----------------- | --------------- |
| 2 nuits | 1400 €            | 700 €           |
| 3 nuits | 1980 €            | 660 €           |
| 4 nuits | 2480 €            | 620 €           |
| 5 nuits | 2900 €            | 580 €           |
| 6 nuits | 3240 €            | 540 €           |
| 7 nuits | 3500 €            | 500 €           |
{ .headers }

<!--
Logique interne :

| Nuit supplémentaire | Supplément |
| ------------------- | ---------: |
| 3e nuit             |     +350 € |
| 4e nuit             |     +300 € |
| 5e nuit             |     +250 € |
| 6e nuit             |     +250 € |
| 7e nuit             |     +200 € |
-->

### Haute saison

- Vacances d’été
- Fêtes de fin d’année
- les week-ends prolongés de 2026/2027 (Pâques, Ascension, Pentecôte, Toussaint,
  Armistice)

Pour les vacances d’été et de fin d’année, les séjours sont de 5 nuits minimum,
sauf en réservation de dernière minute.


| Durée   | Total lot 2 gîtes | Prix par nuitée |
| ------- | ----------------- | --------------- |
| 2 nuits | 1650 €            | 825 €           |
| 3 nuits | 2310 €            | 770 €           |
| 4 nuits | 2880 €            | 720 €           |
| 5 nuits | 3300 €            | 660 €           |
| 6 nuits | 3840 €            | 640 €           |
| 7 nuits | 4200 €            | 600 €           |
{ .headers }

<!--
Logique interne :

| Nuit supplémentaire | Supplément |
| ------------------- | ---------: |
| 3e nuit             |     +450 € |
| 4e nuit             |     +400 € |
| 5e nuit             |     +350 € |
| 6e nuit             |     +300 € |
| 7e nuit             |     +300 € |
-->

## Disponibilités { #dispo }

<!--
<iframe src="https://calendar.google.com/calendar/embed?height=600&wkst=2&ctz=Europe%2FParis&bgcolor=%23ffffff&showTitle=0&showPrint=0&showTabs=0&showCalendars=0&src=NjFiZmQ3ZmM3ZDNkZDExYWU3ZDAwYmJlOTBlZDIxZDU1MTAyNDNmOWI0ZTZhNTE4NmQwNzgyNDA1ZDZmNjJkYUBncm91cC5jYWxlbmRhci5nb29nbGUuY29t&color=%23AD1457" style="border-width:0" width="800" height="600" frameborder="0" scrolling="no"></iframe>
-->

<iframe src="https://calendar.google.com/calendar/embed?height=600&wkst=2&ctz=Europe%2FParis&showPrint=0&showCalendars=0&showTz=0&showTitle=0&hl=fr&src=MTgwODc5MDdhMmVjNmNjZjgwZGMxNjdmYzQ4YTA5OWExMjI2NDc3ODAxNjQ3YzQyNGZjY2U5NjRjODJiMWNhY0Bncm91cC5jYWxlbmRhci5nb29nbGUuY29t&color=%23d50000" style="border-width:0" width="800" height="600" frameborder="0" scrolling="no"></iframe>

<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2833.933701197773!2d5.378472376533459!3d44.74136938137577!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x12cab7b61acc6f8b%3A0xe1155f185160aeb9!2sG%C3%AEte%20Au%20son%20du%20Diois!5e0!3m2!1sfr!2sfr!4v1711377259882!5m2!1sfr!2sfr" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>

## Contacts

N'hésitez pas à nous appeler ou nous écrire pour toutes questions :

- <a href="tel:+33781112176">07 81 11 21 76</a>
- diwawatt@gmail.com

## Réserver { #reserver }

Vous êtes décidé, **remplissez** le formulaire suivant. Nous vous renverrons un
**contrat de location** et une demande de versement d'**Arrhes de 30%** pour
valider votre réservation.

N'hésitez pas à nous appeler si vous avez besoin de renseignement supplémentaire
avant de réserver.

<script src="https://challenges.cloudflare.com/turnstile/v0/api.js" async defer></script>

<form class="booking-form" action="https://booking-form-worker.diwawatt.workers.dev" method="POST">

  <div class="field">
    <label for="lastName">Nom</label>
    <input type="text" id="lastName" name="lastName" required autocomplete="family-name" />
  </div>

  <div class="field">
    <label for="firstName">Prénom</label>
    <input type="text" id="firstName" name="firstName" required autocomplete="given-name" />
  </div>

  <div class="field">
    <label for="email">Email</label>
    <input type="email" id="email" name="email" required autocomplete="email" />
  </div>

  <div class="field">
    <label for="phone">Téléphone</label>
    <input type="tel" id="phone" name="phone" required autocomplete="tel" />
  </div>

  <div class="field">
    <label for="startDate">Date d'arrivée</label>
    <input type="date" id="startDate" name="startDate" required />
  </div>

  <div class="field">
    <label for="nbNights">Nombre de nuits</label>
    <input type="number" id="nbNights" name="nbNights" min="1" step="1" required />
  </div>

  <div class="field">
    <label for="nbAdults">Nombre d'adultes</label>
    <input type="number" id="nbAdults" name="nbAdults" min="1" max="15" step="1" required />
  </div>

  <!-- Turnstile: isolated -->
  <div class="captcha-wrapper">
    <div class="cf-turnstile" data-sitekey="0x4AAAAAACJS-CKeuwybI-2p"></div>
  </div>

  <div class="actions">
    <button type="submit">Réserver</button>
  </div>

</form>
