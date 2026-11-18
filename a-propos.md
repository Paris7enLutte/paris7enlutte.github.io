---
layout: default
title: À propos
permalink: /a-propos/
theme: nuit
---

# À propos

{{ site.title }} est un espace d'échange pour la communauté mobilisée de Paris 7 : étudiantes et étudiants, personnels, enseignantes et enseignants. On y trouve les communiqués, les ressources partagées et l'agenda de la mobilisation, sans passer par les réseaux sociaux.

<section id="inscription" class="encart">
  <h2>Recevoir la lettre</h2>
  <p>Indiquez votre adresse ci-dessous, puis cliquez sur le lien du courriel de confirmation que vous recevrez : l'inscription n'est validée qu'après ce clic.</p>
  <iframe class="brevo-formulaire" src="{{ site.brevo_formulaire }}" title="Formulaire d'inscription à la lettre" loading="lazy"></iframe>
  <p class="petit">Adresse utilisée uniquement pour l'envoi de la lettre, désinscription en un clic depuis chaque numéro. Formulaire hébergé par Brevo. <a href="{{ '/confidentialite/' | relative_url }}">Données personnelles</a>. Le formulaire ne s'affiche pas ? <a href="{{ site.brevo_formulaire }}" target="_blank" rel="noopener">Ouvrir le formulaire</a>.</p>
</section>

## Nous suivre

<ul class="reseaux">
{% for r in site.data.reseaux %}  <li>{% if r.url %}<a class="reseau" href="{{ r.url }}" target="_blank" rel="noopener me">{{ r.nom }}</a>{% else %}<span class="reseau reseau--bientot">{{ r.nom }} <small>bientôt</small></span>{% endif %}</li>
{% endfor %}</ul>

Les réseaux relaient les annonces ; tout reste consultable ici, sans compte.

## Contact

Courriel : <a href="mailto:{{ site.email_contact }}">{{ site.email_contact }}</a>

## Suivre sans s'inscrire

Le [flux RSS]({{ '/feed.xml' | relative_url }}) permet de suivre les nouvelles lettres depuis n'importe quel lecteur de flux, sans communiquer d'adresse.
