
# Comment utiliser Esc@Pad pour produire un support de cours multi-plateformes

## Structure globale d'un cours Culture Numérique

Un cours se décompose en sections et sous-sections. Le niveau sous-sections constitue le niveau "pivot" de la structure d'un [cours Culture NUmérique](http://culturenumerique.univ-lille3.fr/). Chaque sous-section peut être du type et de la forme suivante:  

1. cours simple (texte + images)  
2. vidéo de cours accompagnée de la version texte
3. activité de 3 types possibles:
    - auto-évaluation sous forme de quiz
    - exercice autonome
    - exercice d'approfondissement

RMQ: les 2 derniers types d'exercice incluent un énoncé (texte riche) et un espace pour fournir une réponse sous forme de texte libre



## Cours avec image

Rédigée en MarkDown, c'est un type de sous-section simple consistant en du texte mis en forme et enrichi d'images.

![vue_web_cours](media/vue_web_cours.png)


## Vidéo de cours

[video]( https://vimeo.com/93350435 ){: .cours_video }


Ces éléments de cours consistent en des sous-sections pouvant inclure 1 ou plusieurs vidéos d'animations. Pour qu'un lien vers une vidéo (Vimeo uniquement pour l'instant) soit reconnu comme video de cours,  on utilise le principe des *attribute lists* (cf ci-dessus) en ajoutant la classe `cours_video`:  

```
[Introduction au web](https://vimeo.com/138623497){: .cours_video }
```

**NB:** les liens de videos doivent être de la forme

`https://vimeo.com/1234568`

et non

`https://player.vimeo.com/video/1234568`

La 2e forme est celle du champ "src" des iframes vimeo, mais l'API Vimeo requiert la 1ère forme, et qui est le lien permettant de plus d'accéder à la page vimeo de la video, et donc d'accéder à la chaine, aux autres videos, de liker, partager, etc.


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

## Une sous-section de cours entre 2 activités

Ces activités sont rédigées en GIFT; chaque question est séparée par une ligne vide. La syntaxe Gift a été proposé par l'équipde Moodle pour permettre de gagner du temps dans la rédaction de quizz et de tests. Cette syntaxe est disponible sur [cette page](https://docs.moodle.org/28/en/GIFT_format). Il s'agit d'un format "texte" qui peut s'éditer dans n'importe quel "éditeur de texte" (et non dans un "traitement de texte").

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
