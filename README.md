# Oupeinpo GitHub Pages API

Page statique GitHub Pages pour envoyer des images vers l'API locale Oupeinpo.

## Architecture

```text
GitHub Pages
  -> formulaire HTML/CSS/JavaScript
  -> POST vers API HTTPS Tailscale
  -> traitement Oupeinpo sur le Mac
  -> images generees publiques
  -> rapport prive par e-mail Proton Bridge
```

API actuellement configuree dans `docs/index.html` :

```text
https://macbook-air-de-john.tailc688f6.ts.net
```

Cette URL est privee Tailscale : elle fonctionne seulement pour les appareils connectes au meme tailnet.

## Publication GitHub Pages

Option recommandee maintenant : publier avec GitHub Actions.

Dans les reglages GitHub du depot :

```text
Settings -> Pages -> Build and deployment
Source: GitHub Actions
```

Le workflow `.github/workflows/pages.yml` publie le contenu du dossier `docs`.

Ancienne option possible, sans workflow :

```text
Settings -> Pages -> Build and deployment
Source: Deploy from a branch
Branch: main
Folder: /docs
```

L'URL aura la forme :

```text
https://chaosmosis.github.io/NOM_DU_DEPOT/
```

## Confidentialite

La page GitHub n'heberge aucune image source.

Les images envoyees passent vers l'API Oupeinpo, sont traitees sur le Mac, puis supprimees apres traitement.

La page publique de resultat ne contient que les images generees de cluster.

Le rapport ACP avec miniatures est envoye par e-mail au participant.

## Licence

AGPL-3.0-or-later.
