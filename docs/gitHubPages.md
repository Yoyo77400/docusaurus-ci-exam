# GitHub Pages

- Generation de github pages configuré via le github action dans les paramètres du repo

- Correspond au code suivant dans le fichier de workflow: 

```
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

