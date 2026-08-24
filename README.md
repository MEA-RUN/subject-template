# Subject template

Ce dépôt est le point de départ d'un sujet Manta Academy. Aucun projet Nuxt
n'est nécessaire ici : Reef construit et publie le site à partir du contenu.

## Créer un sujet

1. Créez un dépôt depuis ce template.
2. Ajoutez les versions françaises dans `subjects/fr` et anglaises dans
   `subjects/en`.
3. Placez les images et autres fichiers dans `assets`.
4. Copiez `metadata.example.yml` vers `metadata.yml` et listez les outils à
   afficher dans le panneau droit. Le fichier peut contenir `tools: []`.
5. Lancez manuellement l'action **Create Reef site**.

Le site généré porte par défaut le nom `<nom-du-dépôt>-site`. Il est recréable :
les sujets, assets et outils doivent donc toujours être modifiés dans ce dépôt,
jamais dans le dépôt généré.

## Mettre le site à jour

- **Update Reef content** remplace les sujets et assets du site généré.
- **Update Reef tools** retélécharge tous les outils déclarés dans
  `metadata.yml`.

Les workflows nécessitent les secrets d'organisation `REEF_APP_CLIENT_ID` et
`REEF_APP_PRIVATE_KEY`. L'application GitHub doit être installée sur les dépôts
source et générés avec les permissions `Administration: write`,
`Contents: write`, `Pages: write` et `Metadata: read`.

## Structure

```text
assets/
metadata.yml
subjects/
  en/
  fr/
```

Un exemple minimal de sujet est disponible dans chaque dossier de langue.
