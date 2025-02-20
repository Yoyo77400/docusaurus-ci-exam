# Initialisation du repository Git


## Création de l'application et du répository

- Création de l'application avec la commande:

```
    npx create-docusaurus@latest docusauru-ci-exam
```

- Création du repository en public sur GitHub. Yoyo77400/docusaurus-ci-exam.git
- Création du dossier local du projet
- Initialisation du dépot git local avec la commande: 
```git
    git init
```

## Liaison avec le git distant

```git
    git add .
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/Yoyo77400/docusaurus-ci-exam.git
    git push -u origin main
```