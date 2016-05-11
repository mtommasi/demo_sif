TITLE: Module de cours test 1
MENUTITLE: Module 1
AUTHOR: Culture Numérique
LANGUAGE: fr

_Exemple de cours rédigé en utilisant la syntaxe MarkDown et suivant la convention Esc@Pad permettant de générer un cours complet._


# Rappels sur Internet, le Web et HTML
## Le web
[video]( https://player.vimeo.com/video/138623497 ){: .lien_video } 
Le web, c'est sans doute l'application informatique qui a rencontré le plus grand succès.
C'est une utilisation particulière  d'internet. Il a été inventé par Tim Berners Lee au début des années 90. C'est d'abord un moyen de communication entre personnes qui permet de s'échanger des informations décrites dans des documents . Il est fréquent de constater une confusion entre Internet et le Web. Or, si le web utilise Internet, il n'est pas la seule application à le faire, le mail par exemple est un autre service qui utilise Internet. Socialement, le web a pris une place considérable dans nos vies. Sur cette application au départ très simple se sont bâties d'autres applications dans tous les domaines d'activités : pour le commerce, le marketing, la recherche d'emploi, le travail à distance et la collaboration... C'est un vecteur important de développement économique aujourd'hui. C'est aussi par des applications web que l'état et les administrations offrent leurs services aux citoyens. C'est encore par les applications sociales du web que nous communiquons dans notre vie privée. Maîtriser les technologies du web est important pour comprendre les enjeux, saisir des opportunités, éviter des pièges... Naviguer sur le web fait aujourd'hui partie du quotidien de chacun d'entre nous. Ce chapitre propose d'en expliquer le fonctionnement pour nous permettre d'avoir des comportements responsables et de garder la maîtrise de ce que nous faisons.

![Internet](media/Internet.jpg) 

*Réprésentation du réseau internet*


```activité
// question: 159977  name: La toile et ses fils
::La toile et ses fils::[html]<p>Dans l'image du web représentée par une toile d'araignée, les fils sont \:</p>{
	=<p>des liens</p>
	~<p><strong id\="docs-internal-guid-566566e9-d108-1f1b-8d6f-529e33dacd53" style\="font-weight\: normal;"><span style\="font-size\: 14.666666666666666px; font-family\: Arial; color\: \#434343; background-color\: transparent; font-weight\: 400; font-style\: normal; font-variant\: normal; text-decoration\: none; vertical-align\: baseline; white-space\: pre-wrap;">des câbles du réseau internet</span></strong></p>
}


// question: 159978  name: La toile et ses noeuds
::La toile et ses noeuds::[html]<p>Dans l'image du web représentée par une toile d'araignée, les nœuds sont \:</p>{
	=<p>des ressources</p>
	~<p><span style\="font-weight\: normal;"><span style\="font-size\: 14.666666666666666px; font-family\: Arial; color\: \#434343; background-color\: transparent; font-weight\: 400; font-style\: normal; font-variant\: normal; text-decoration\: none; vertical-align\: baseline; white-space\: pre-wrap;">des ordinateurs</span></span></p>
}

// question: 159983  name: Les échanges sur le web
::Les échanges sur le web::[html]<p>Que s'échangent les ordinateurs sur le Web ?</p>{
	~%33.33333%<p>Des ressources</p>
	~%33.33333%<p>Des images</p>
	~%33.33333%<p>Des textes</p>
	####<p>Les trois !</p>\n<p>Dans ce contexte du web, le mot ressource désigne à la fois des textes, des images, des sons, ... C'est ce mot qu'on retrouve dans la signification de l'acronyme URL \: Uniform Resource Locator</p>
}
```

```activité-avancée
::Tim Berners-Lee::[html]<div>
	<p>En vous aidant par exemple de cette ressource : </p>
	<p>
	<a target="_blank" href="http://home.web.cern.ch/fr/topics/birth-web">http://home.web.cern.ch/fr/topics/birth-web</a>
	</p>
	<p>Faites quelques recherches sur <b>Tim Berners-Lee</b> et l'origine du web et répondez aux questions suivantes :
</p>
      <ol>
        <li>Quelle était la spécialité professionnelle de Tim Berners-Lee ?</li>
        <li>Que contenait le premier site web ?</li>
        <li>En quelle année a-t-il été créé ?</li>
      </ol>
    </div>
{####<p>Contrairement à ce qu'on pourrait imaginer, Tim Berners-Lee n'était pas informaticien mais <b>physicien</b>. Il était chercheur en physique nucléaire au CERN dans les années 80. Son objectif était de faciliter le transfert de connaissance dans la communauté scientifique internationale.</p><p>Le premier site réellement opérationnel décrivait les principales caractéristiques du web et expliquait comment accéder aux documents d'autres personnes et comment configurer son propre serveur.</p><p>Les travaux ont démarré en 1989, le premier site a été mis en ligne en <b>1991</b> mais c'est en 1993 que le premier navigateur au sens ou nous les manipulons aujourd'hui est apparu.</p>}
```
 


## HTML

### HTML: contenu, structure, liens
[video]( https://player.vimeo.com/video/138623721 ){: .lien_video } 
Allons maintenant voir plus en détail le fonctionnement ; le langage `html` a plusieurs caractéristiques très intéressantes. Nous avons vu qu'il permettait d'introduire des hyperliens dans un document, mais il possède d'autres atouts.


C'est un langage de description de document , c'est à dire qu'il permet d'expliquer comment le document est construit et donc comment un logiciel comme un navigateur peut l'afficher. Concrètement, `html` permet d'ajouter au contenu texte des éléments de structure du type : ce paragraphe est un titre, celui-là est un sous-titre, cet  est une légende, ce mot doit être mis en exergue...
Cette distinction contenu/structure est essentielle, elle est présente dans de nombreux domaine et nous y reviendrons souvent. La structure permet d'ajouter du sens aux parties de textes et à l'aide de règles de résentation de rendre une page `html` affichable sur de nombreux types d'écrans. Le navigateur calcule alors la présentation adaptée, par exemple pour une tablette, un smartphone ou un grand écran d'ordinateur.

En français la traduction de `html` est : langage de balisage pour documents hypertexte. Les balises vont indiquer la structure du document en titres, paragraphes etc ainsi que des liens vers d'autres ressources du Web. Les documents sont donc des textes décrivant des documents hypertexte. Mais que fait ensuite le client, le navigateur avec ce document hypertexte qu'il vient de recevoir ?

Grâce à la description faite du document et en fonction de ses capacités le navigateur va pouvoir recomposer le document et vous l'afficher. Les pages web que votre navigateur affiche sont des textes avec le plus souvent des images, formant un document complet. En fait ce document est réalisé par l'assemblage de nombreuses ressources. En effet, le langage `html` permet également de spécifier l'insertion d'images (ou d'autres ressources) à différents endroits d'un document. Les images ne sont pas à proprement parler insérées dans le document principal, mais un balisage indique qu'à cet endroit il faudra insérer une image.



```activité

// Question vide de type description (sans {}) pour présenter le support des questions suivantes
::Exercice::[html]
<p>Rendez-vous sur la page <a target="_blank" href="http://culturenumerique.univ-lille3.fr/activitesWeb/html/">http://culturenumerique.univ-lille3.fr/activitesWeb/html/</a> <br />Lisez, observez, gardez les pages ouvertes dans des onglets, puis répondez aux questions du quizz suivant </p>


// question: 283  name: Au delà du contenu
::Au delà du contenu::[html]<p>Pourquoi peut-on créer facilement une table des matières ou construire la liste des liens d’un document HTML ?</p>{}


// question: 284  name: Décrire un document
::Décrire un document::[html]<p>Pourquoi s’échanger une description de document plutôt qu’un document lui-même est plus adéquat au Web ?</p>{
	~%33.33333%<p>tous les clients n’ont pas la même capacité d’affichage</p>
	~%33.33333%<p>la description contient plus d’informations \: structure + contenu</p>
	~%33.33333%<p>la structure permet d'ajouter du sens (ceci est un titre, etc...) explicitement.</p>
}
```

```activité-avancée
::Activité sur les serveurs::[markdown]
Rendez-vous sur la page :
(pageServeurs.html)[http://culturenumerique.univ-lille3.fr/activitesWeb/html/pageServeurs.html]
Lisez, observez et répondez aux questions posées...
{}
```

