# Gestion des GIT Hub Actions

## Initialisation

- Création d'un dossier .github/workflow
- Dans ce dernier, création du fichier docusaurus-pipeline.yml

## Création des 2 tâches pour l'intégration continue

- Initilisation du projet de CI avec: 
```
    name: docusaurus
    run-name: ${{ github.actor }} Docusaurus GitHub Action
```
-  Création de la première action pour build le projet à chaque push sur main
```
on:
  push:
    branches:
      - main

jobs:
  Run-Docusaurus:
    build:
      runs-on: ubuntu-latest
      steps:
        - name: run-docusaurus
        - uses: actions/setup-node@v4
          with:
            node-version: '20'
        - run: npm run build
```

