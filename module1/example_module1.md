TITLE: Module de cours test 1
MENUTITLE: Module Test 1
AUTHOR: Culture Numérique
LANGUAGE: fr

_Exemple de cours rédigé en utilisant la syntaxe MarkDown et suivant la convention Esc@Pad permettant de générer un cours complet._


# Comment utiliser Esc@Pad pour produire un support de cours multi-plateformes


## Syntaxe pour éditer un contenu de cours Esc@Pad

[video]( https://vimeo.com/93350435 ){: .cours_video }

Nous détaillons ici la chaine éditoriale adoptée pour la production des modules mis à dispositions sur ce dépôt.  
Nous utilisons un fichier dit "maitre" comme matrice de base pour générer le cours. La syntaxe employée est basée sur le format MarkDown, que nous avons étendu pour nos besoins spécifiques. Ces ajouts consistent en des conventions décrites ci-dessous et l'usage d'extensions proposées par la [librairie Python de MarkDown](https://pythonhosted.org/Markdown/extensions).


## Structure globale d'un cours Culture Numérique
Un cours se décompose en sections et sous-sections. Le niveau sous-sections constitue le niveau "pivot" de la structure d'un cours Culture NUmérique. Chaque sous-section peut être du type et de la forme suivante:  

1. cours simple (texte + images)  
2. vidéo de cours accompagnée de la version texte
3. activité de 3 types possibles:
    - auto-évaluation sous forme de quiz
    - exercice autonome
    - exercice d'approfondissement

RMQ: les 2 derniers types d'exercice incluent un énoncé (texte riche) et un espace pour fournir une réponse sous forme de texte libre


## Cours simple

Rédigée en MarkDown, c'est un type de sous-section simple consistant en du texte mis en forme et enrichi d'images.
Par rapport au MArkdown simple, nous utilisons les fonctions supplémentaires décrites ci-après.


### ajouter des classes CSS

Avec des [Attribute list](https://pythonhosted.org/Markdown/extensions/attr_list.html): Pour permettre d'ajouter des classes CSS à une image ou à un bloc de texte, pour permettre une mise en page enrichie.
Un exemple pour ajouter un attribut en ligne à un lien:  
`[link](http://example.com){: class="foo bar" .titre title="Some title!" }`  
qui produit le HTML suivant:  
`<p><a href="http://example.com" class="foo bar titre" title="Some title!">link</a></p>`  

Notez que pour ajouter des classes on peut soit spécifier `.une_classe` ou `class='une_classe``


### Commentaires invisibles
En utilisant simplement les commentaires HTML:

        <!-- On pourrait aussi mentionner les lol cats dans cette section non ? -->

Le commentaire suivant ne sera donc pas visible dans le rendu HTML final.
<!-- Il faudrait vraiment enrichir cette documentation de quelques Gifs animés -->        


### Vidéo de cours

Ces éléments de cours consistent en des sous-sections pouvant inclure 1 ou plusieurs vidéos d'animations. Pour qu'un lien vers une vidéo (Vimeo uniquement pour l'instant) soit reconnu comme video de cours,  on utilise le principe des *attribute lists* (cf ci-dessus) en ajoutant la classe `cours_video`:  

    [Introduction au web](https://vimeo.com/138623497){: .cours_video }

ou  

    [Introduction au web](https://vimeo.com/138623497){: class="cours_video" }

Ce lien doit être placé à l'intérieur d'une sous-section. Une sous-section peut bien sûr comporter plusieurs vidéos de cours.

Ces liens vidéos font l'objet d'un traitement spécifique selon le type d'export:
* export Site Vitrine HTML: on génère un code d'iframe qui permet de lire le/les vidéo/s sans quitter la page courante;
* pour l'export Moodle/IMSCC, le plugin Viméo de Moodle permet de transformer le lien vidéo en iframe automatiquement:
![video_moodle](media/3.vue_cours_avec_video.png)

**NB:** les liens de videos doivent être de la forme

`https://vimeo.com/1234568`

et non

`https://player.vimeo.com/video/1234568`

La 2e forme est celle du champ "src" des iframes vimeo, mais l'API Vimeo requiert la 1ère forme, et qui est le lien permettant de plus d'accéder à la page vimeo de la video, et donc d'accéder à la chaine, aux autres videos, de liker, partager, etc.

## Sous-sections d'activités

Les activités peuvent être de 3 types:

- auto-évaluation pour vérifier la compréhension du cours: `comprehension`
- exercices de recherche autonome : `activité`
- Exercices d'approfondissement: `activité-avancée`

Pour le découpage des activités, nous n'utilisons plus les `##` de la syntaxe markdown, mais les "fenced code blocks" en spécifiant le type d'activité  juste à côté des "backticks":

        ```comprehension

        ```

ou

        ```activité-avancée

        ```


### Syntaxe GIFT

Ces activités sont rédigées en GIFT; chaque question est séparée par une ligne vide. La syntaxe Gift a été proposé par l'équipde Moodle pour permettre de gagner du temps dans la rédaction de quizz et de tests. Cette syntaxe est disponible sur [cette page](https://docs.moodle.org/28/en/GIFT_format). Il s'agit d'un format "texte" qui peut s'éditer dans n'importe quel "éditeur de texte" (et non dans un "traitement de texte").

Exemple:

        ```activité-avancée

        ::Représentation numérique::La représentation numérique d'un livre peut inclure des données qui ne se limitent pas au texte. Donnez quelques exemples
        {
        #### Le genre, la date de création, ...
        }

        ::Fonctionnalités d'un éditeur de textes::
        [html]<p>Parmi les  fonctionnalités suivantes, lesquelles sont possibles ?</p>
        {
        ~%25%copier/couper/coller#tous les éditeurs le permettent
        ~%25%rechercher et remplacer#très souvent disponible
        ~%25%avancer de mots en mots#souvent par la conjonction CRTL-flèches
        ~%25%corriger l'orthographe#certains le font
        ~%-100%mettre en gras#l'éditeur ne permet pas d'enregistrer des mises en forme (il est possible toutefois d'écrire des commandes de mise en forme : un mot n'est pas en gras mais un texte dans un langage peut exprimer l'ordre de mettre en gras)
        }
        ```

### HTML et MarkDown dans les questions rédigées en GIFT

Dans les questions rédigées en GIFT il est possible de rédiger le texte au format HTML ou Markdown en spécifiant devant chaque bloc la syntaxe (voir explications à la fin de [ce paragraphe de la documentation Moodle sur le format GIFT](https://docs.moodle.org/28/en/GIFT_format#Percentage_Answer_Weights)).

Dans le cas du Markdown, il y a cependant une limitation pour les listes (simples ou numérotées). En Markdown il faut laisser une ligne vide avant de commencer une liste:
```
Ingrédients:

- carottes
- pommes de terre

```
... or dans la spécification GIFT, une ligne vide sépare 2 questions distinctes. Les lignes vides pourront donc être indiquées dans un énoncé en GIFT avec le caractère de retour à la ligne "echappé" `\n`. Par exemple:
```
Ingrédients:
\n
- carottes
- pommes de terre

```  
Qui permettra donc d'avoir une liste dans l'export HTML:
```
Ingrédients:
<ul>
<li>carottes</li>
<li>pommes de terre</li>
</ul>
```

# Exemples d'activité

Dans les sous-sections suivantes, retrouvez une série d'exemple d'activités des 2 types (simple et avancées.). N'hésitez-pas à vous inspirer de ces exemples et à les prendre comme point de départ pour créer vos propres quiz et activités.

```comprehension
::Représenter et manipuler::
[markdown]
**Représenter et manipuler**
Les traitements possibles dépendent fortement des choix de représentation
{T}

::Quelles données ?::
[markdown]
**Quelles données ?**
La représentation numérique d'un livre peut inclure des données qui ne se limitent pas au contenu textuel. Donnez quelques exemples.
{#### Le genre, la date de création, l'éditeur, ...}

::De la variété ?::
[markdown]
**De la variété ?**
Il n'existe qu'une seule façon de représenter numériquement un livre.
{F #Représenter une information est le résultat de nombreux choix}

::Comment choisir ?::
[markdown]
**Comment choisir ?**
Donnez des exemples de critères qui peuvent gouverner le choix d'une représentation numérique.
{#### la concision, la pertinence (permettre des traitements voulus), l'efficacité (les traitements sont réalisés rapidement, la confidentialité (l'accès aux données  peut être contrôlé),...}

::Qui choisit ? ::
[markdown]
**Qui choisit ?**
Les choix de représentations sont faits par
{
~Les informaticiens #non pas seuls car intervient aussi l'utilisation métier des objets représentés
~Les experts métier #non pas seuls car il faut des spécialistes des données numériques et des algorithmes
=Les deux #oui et souvent aussi des chercheurs, des entreprises, ...
}
```

```activité
::Une tâche complexe::
[markdown]
**Une tâche complexe**
Représenter et normaliser est une tâche complexe : l'exemple de HTML. En vous rendant sur les pages wikipedia de [HTML](https://fr.wikipedia.org/wiki/Hypertext_Markup_Language) et du [W3C](https://fr.wikipedia.org/wiki/World_Wide_Web_Consortium). Répondez aux questions suivantes :
- Quelle est l'origine de `HTML` ?
- Qui développe et publie les spécifications `HTML` depuis 1995 ?
- Quelle est la version la plus récente de `HTML` et son année de parution ?
- Qui participe au développement du standard `HTML` au `W3C` ?
- Quelles sont les étapes pour arriver à être une recommandation ?
- Qui est responsable du standard `css` pour les feuilles de style ?
{#### origine au CERN ; Le W3C développe le HTML depuis 1995 ; HTML5 en 2014 ; industriels, éditeurs logiciels, chercheurs, entreprises du Web, ... ; brouillon, appel, candidat, proposition et recommandation ; le W3C.}
```
