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
    branch:
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

        - name: Upload des artefacts pour le déploiement
        - uses: actions/upload-pages-artifact@v3
          with:
            path: ./build
  
  Deploy-Docusaurus:
    deploy:
    needs: build
    runs-on: ubuntu-latest

    steps:
      - name: Déployer sur GitHub Pages
        uses: actions/deploy-pages@v4
```

