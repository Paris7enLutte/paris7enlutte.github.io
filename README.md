# Paris 7 En lutte

Site : https://paris7enlutte.github.io/
Contact : mob2026paris7@gmail.com

Site gratuit et sans serveur, publié par GitHub Pages. Chaque fichier enregistré dans ce dépôt met le site à jour en une à deux minutes. La lettre d'information part par Brevo, depuis le compte du collectif.

## Où modifier quoi

| Rubrique | Fichier |
|---|---|
| Agenda | `_data/agenda.yml` |
| Communiqués | `_data/publications.yml` |
| Université populaire (lieux, formulaire, planning) | `_data/universite_populaire.yml` |
| Réseaux sociaux (page À propos) | `_data/reseaux.yml` |
| Galerie photo | `_data/galerie.yml` + photos dans `assets/galerie/` |
| Numéros de la lettre (page Ressources) | `_posts/` |
| Titre, description, courriel de contact, formulaire Brevo | `_config.yml` |

Sur GitHub : ouvrir le fichier, cliquer sur le crayon, modifier, puis **Commit changes**. Les fichiers `.yml` sont sensibles aux espaces en début de ligne : recopier la forme d'une entrée existante.

## Publier un numéro de la lettre

1. Dans `_posts/`, créer `AAAA-MM-JJ-titre-court.md` (**Add file > Create new file**), avec cet en-tête :

```
---
title: "Titre de la lettre"
chapo: "Phrase d'accroche facultative."
numero: 2
---
```

2. Rédiger le texte en Markdown sous l'en-tête et enregistrer : le numéro paraît sur le site, page Ressources.
3. Dans Brevo, **Campagnes > Créer une campagne > E-mail**, destinataires : liste « Abonnés lettre ». Pour le contenu, choisir **Vos templates > Modèle lettre Paris 7 En lutte**, puis remplacer dans le code les textes d'exemple (numéro, date, titre, accroche, texte, rendez-vous) par ceux du numéro.
4. Dans les réglages de la campagne, désactiver le suivi des ouvertures et des clics (engagement pris sur la page Données personnelles).
5. S'envoyer un test, puis programmer ou envoyer. Le lien de désinscription est ajouté par Brevo.

## Abonnés

La liste « Abonnés lettre » se gère dans Brevo (**Contacts**). Les inscriptions arrivent par le formulaire de la page À propos ou par le QR code, avec double confirmation par courriel. L'offre gratuite de Brevo permet 300 courriels par jour.

## Markdown

`## Intertitre` · `**gras**` · `*italique*` · `[lien](https://...)` · `- puce` · `> citation` · `![image](/assets/photo.jpg)`

## Prévisualiser sur un ordinateur (facultatif)

`bundle install`, puis `bundle exec jekyll serve`. GitHub Pages n'en a pas besoin.
