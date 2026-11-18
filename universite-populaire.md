---
layout: default
title: Université populaire
permalink: /universite-populaire/
theme: up
description: Proposer un cours, un atelier ou une projection à l'université populaire du campus des Grands Moulins.
---

# Université populaire

L'université populaire du campus des Grands Moulins (Paris 13e) est ouverte à toutes et à tous. Étudiantes, étudiants, personnels, enseignantes, enseignants et personnes extérieures peuvent y proposer un cours, un atelier, une lecture, une projection ou une discussion.

<div class="up-etapes">
  <div class="up-etape"><span class="up-num">1</span><strong>Proposer</strong><p>Remplir le formulaire ci-dessous avec trois choix de dates et d'horaires. Un créneau dure deux heures.</p></div>
  <div class="up-etape"><span class="up-num">2</span><strong>Confirmer</strong><p>Les chargés de régulation recontactent les organisateurs pour fixer la date et le lieu, en évitant les chevauchements.</p></div>
  <div class="up-etape"><span class="up-num">3</span><strong>Annoncer</strong><p>Les cours confirmés figurent dans le planning et dans l'<a href="{{ '/agenda/' | relative_url }}">agenda</a> du site.</p></div>
</div>

<p class="up-boutons">
  <a class="bouton" href="{{ site.data.universite_populaire.planning }}" target="_blank" rel="noopener">Voir le planning des cours</a>
  <a class="bouton bouton--clair" href="{{ site.data.universite_populaire.formulaire }}" target="_blank" rel="noopener">Ouvrir le formulaire dans un nouvel onglet</a>
</p>

## Les lieux

<ul class="up-lieux">
{% for l in site.data.universite_populaire.lieux %}  <li><strong>{{ l.nom }}</strong><span>{{ l.adresse }}</span>{% if l.note %}<em>{{ l.note }}</em>{% endif %}</li>
{% endfor %}</ul>

<section id="formulaire" class="up-formulaire">
  <h2>Proposer une intervention</h2>
  <iframe src="{{ site.data.universite_populaire.formulaire }}" title="Formulaire d'inscription des cours de l'université populaire" loading="lazy"></iframe>
  <p class="petit">Formulaire hébergé par Framaforms (association Framasoft). Le numéro de téléphone demandé n'est accessible qu'aux coordinateurs de l'université populaire. Questions : <a href="mailto:{{ site.email_contact }}">{{ site.email_contact }}</a>.</p>
</section>
