---
layout: default
title: Ressources
permalink: /ressources/
theme: papier
---

# Ressources

Documents et numéros de la lettre, du plus récent au plus ancien. Pour les recevoir par courriel : [s'abonner]({{ '/a-propos/' | relative_url }}#inscription).

<div class="vignettes">
{% for lettre in site.posts %}
  <a class="vignette" href="{{ lettre.url | relative_url }}">
    <span class="vignette-meta">{% if lettre.numero %}N° {{ lettre.numero }} · {% endif %}{{ lettre.date | date: "%d/%m/%Y" }}</span>
    <strong>{{ lettre.title }}</strong>
    {% if lettre.chapo %}<span class="vignette-texte">{{ lettre.chapo }}</span>{% endif %}
  </a>
{% endfor %}
</div>

{% if site.posts.size == 0 %}<p>Le premier numéro paraîtra prochainement.</p>{% endif %}

## Galerie

{% assign photos = site.data.galerie %}
{% if photos and photos.size > 0 %}
<div class="galerie">
{% for ph in photos %}  <figure>
    <a href="{{ '/assets/galerie/' | append: ph.fichier | relative_url }}" data-legende="{{ ph.legende | escape }}{% if ph.credit %} · {{ ph.credit | escape }}{% endif %}"><img src="{{ '/assets/galerie/' | append: ph.fichier | relative_url }}" alt="{{ ph.legende | escape }}" loading="lazy"></a>
    <figcaption>{{ ph.legende }}{% if ph.date %} <span>{{ ph.date | date: "%d/%m/%Y" }}</span>{% endif %}</figcaption>
  </figure>
{% endfor %}</div>
<dialog id="visionneuse" class="visionneuse" aria-label="Photo agrandie">
  <button type="button" class="vis-fermer" aria-label="Fermer">×</button>
  <button type="button" class="vis-prec" aria-label="Photo précédente">‹</button>
  <figure><img alt=""><figcaption></figcaption></figure>
  <button type="button" class="vis-suiv" aria-label="Photo suivante">›</button>
</dialog>
<script>
(function () {
  var liens = Array.from(document.querySelectorAll('.galerie a')), d = document.getElementById('visionneuse'), i = 0;
  if (!d.showModal) return;
  var img = d.querySelector('img'), leg = d.querySelector('figcaption');
  function voir(n) { i = (n + liens.length) % liens.length; img.src = liens[i].href; img.alt = liens[i].querySelector('img').alt; leg.textContent = liens[i].dataset.legende; }
  liens.forEach(function (a, n) { a.addEventListener('click', function (ev) { ev.preventDefault(); voir(n); d.showModal(); }); });
  d.querySelector('.vis-fermer').onclick = function () { d.close(); };
  d.querySelector('.vis-prec').onclick = function () { voir(i - 1); };
  d.querySelector('.vis-suiv').onclick = function () { voir(i + 1); };
  d.addEventListener('click', function (ev) { if (ev.target === d) d.close(); });
  d.addEventListener('keydown', function (ev) { if (ev.key === 'ArrowLeft') voir(i - 1); if (ev.key === 'ArrowRight') voir(i + 1); });
})();
</script>
{% else %}
<p class="galerie-vide">Les photos de la mobilisation seront publiées ici.</p>
{% endif %}
