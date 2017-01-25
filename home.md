
## Démonstration pour la SIF... 

Ça marche, même pas peur de **l'effet démo**...

Template de cours pour créer des cours avec Esc@Pad

## Créer son programme de cours avec Esc@Pad

1. Créez-vous un compte sur un gestionnaire de version de fichier de type 'git' (GitHub, Gitlab, Bitbucket, etc).
1. Dupliquez ce dépôt de fichier et importez le. Si vous utilisez GitHub, faites simplement "Fork"
2. La structure de ce template est simple:
  - un programme de cours est contenu dans un dépôt de type Git (le dépôt que vous avec dupliqué)
  - un programme de cours se décompose en "modules" chaqun contenu dans un dossier nommé `moduleX` avec `X` le numéro de chaque module qui déterminera l'ordre dans lequel les modules sont rangés.
  - dans chaque dossier de module, il y a un fichier `lenomdemoncours.md` et un dossier `media` contenant les images insérées dans votre chaque module de cours. La syntaxe utilisé pour éditer un module de cours est expliquée sur [cette page](http://escapad.univ-lille3.fr/documentation/)
3. dans le fichier home.md, remplacer le texte par le contenu de votre page d'accueil.
4. pour personnaliser le logo remplacez le fichier `logo.png` par le fichier de votre choix que vous renommerez `logo.png|jpg|gif` en fonction du type d'image utilisée.
5. enfin, pour personnaliser le titre de votre programme de cours, éditer le fichier `title.md` et, sans le renommer, insérez votre titre en première ligne.
6. pour générer votre site, rendez-vous sur le site http://escapad.univ-lille3.fr/admin, loguez vous avec les accès qui vous ont été fournis, et cliquez sur "Ajouter un dépôt".
7. renseignez le champs "url du dépôt", modifiez au besoin la branche par défaut. Validez.
8. Vous pouvez à présent générer un site vitrine de votre cours en cliquant sur "Build site". Les archives d'export (IMS, etc) sont disponibles à l'intérieur de ce site.
9. Le lien "Build site" peut être utilisé comme webhook pour les plateformes Git le supportant (framagit, github).
