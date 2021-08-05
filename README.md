# projet-jquery
veille: jQuery-CSS-Animation-Transition

Que signifie le DOM?
Le DOM, qui signifie Document Object Model (c'est-à-dire "modèle d'objet de document", en français), est une interface de programmation qui est une représentation du HTML d'une page web et qui permet d'accéder aux éléments de cette page web et de les modifier avec le langage JavaScript.

Comment est-il organisé?:
Prenons ce morceau de code HTML et regardons ce qui va se passer :


<body>

    <div>

        <h1>Bonjour à tous</h1>

        <p>Bienvenue dans ce tutoriel sur le DOM</p>

        <a href="https://fr.wikipedia.org">Wikipedia</a>

    </div>

</body>
1 Le document HTML est analysé par le navigateur.
2 Pour faire simple on va dire que pour chaque élément HTML trouvé, le navigateur instancie un objet JavaScript et le place dans un arbre. Il constitue ainsi un arbre d'instances   d'objets JavaScript à partir du contenu HTML.
3 L'arbre est mis à disposition du développeur à partir d'une instance d'un objet spécifique qui s'appelle document.
4 Le développeur web n'a plus qu'à récupérer les adresses des instances des objets JavaScript pour les manipuler et modifier le document HTML (* celui du navigateur).
5 Il peut aussi choisir une instance pour intercepter les événements qui pourraient être déclenchés depuis un élément HTML.

Quelles sont les méthodes permettant d’accéder aux éléments du DOM?
1. Accéder à un élément à partir de son sélecteur CSS associé
  La façon la plus simple d’accéder à un élément dans un document va être de la faire en le ciblant avec le sélecteur CSS qui lui est associé.
  Deux méthodes nous permettent de faire cela : les méthodes querySelector() et querySelectorAll() qui sont des méthodes du mixin ParentNode et qu’on va pouvoir implémenter à     partir des interfaces Document et Element.
  La méthode querySelector() retourne un objet Element représentant le premier élément dans le document correspondant au sélecteur (ou au groupe de sélecteurs) CSS passé en       argument ou la valeur null si aucun élément correspondant n’est trouvé.
  La méthode querySelectorAll() renvoie un objet appartenant à l’interface NodeList. Les objets NodeList sont des collections (des listes) de nœuds.
  
2. Accéder à un élément en fonction de la valeur de son attribut iD
  La méthode getElementById() est un méthode du mixin NonElementParentNode et qu’on va implémenter à partir d’un objet Document.
  Cette méthode renvoie un objet Element qui représente l’élément dont la valeur de l’attribut id correspond à la valeur spécifiée en argument.
  La méthode getElementById() est un moyen simple d’accéder à un élément en particulier (si celui-ci possède un id) puisque les id sont uniques dans un document.
  
3. Accéder à un élément en fonction de la valeur de son attribut class
  Les interfaces Element et Document vont toutes deux définir une méthode getElementsByClassName() qui va renvoyer une liste des éléments possédant un attribut class avec la       valeur spécifiée en argument. La liste renvoyée est un objet de l’interface HTMLCollection qu’on va pouvoir traiter quasiment comme un tableau.
  En utilisant la méthode getElementsByClassName() avec un objet Document, la recherche des éléments se fera dans tout le document. En l’utilisant avec un objet Element, la       recherche se fera dans l’élément en question
4. Accéder à un élément en fonction de son identité
   La méthode getElementsByTagName() permet de sélectionner des éléments en fonction de leur nom et renvoie un objet HTMLCollection qui consiste en une liste d’éléments            correspondant au nom de balise passé en argument. A noter que cette liste est mise à jour en direct (ce qui signifie qu’elle sera modifiée dès que l’arborescence DOM le          sera).
  Cette méthode est définie différemment par les interfaces Element et Document (pour être tout à fait précis, ce sont en fait deux méthodes qui portent le même nom, l’une         définie dans Document, l’autre dans Element).
  Lorsqu’on utilise getElementsByTagName() avec un objet Document, la recherche se fait dans tout le document tandis que lorsqu’on utilise getElementsByTagName() avec un objet     Element, la recherche se fera dans l’élément en question seulement.
5. Accéder à un élément en fonction de son attribut name
  Finalement, l’interface Document met également à notre disposition la méthode getElementsByName() qui renvoie un objet NodeList contenant la liste des éléments portant un       attribut name avec la valeur spécifiée en argument sous forme d’objet.
  On va pouvoir utiliser cette méthode pour sélectionner des éléments de formulaire par exemple.
6. Accéder directement à des éléments particuliers avec les propriétés de Document
   Finalement, l’interface Document fournit également des propriétés qui vont nous permettre d’accéder directement à certains éléments ou qui vont retourner des objets contenant    des listes d’éléments.
   Les propriétés qui vont le plus nous intéresser ici sont les suivantes :

  La propriété body qui retourne le nœud représentant l’élément body ;
  La propriété head qui retourne le nœud représentant l’élément head ;
  La propriété links qui retourne une liste de tous les éléments a ou area possédant un href avec une valeur ;
  La propriété title qui retourne le titre (le contenu de l’élément title) du document ou permet de le redéfinir ;
  La propriété url qui renvoie l’URL du document sous forme de chaine de caractères ;
  La propriété scripts qui retourne une liste de tous les éléments script du document ;
  La propriété cookie qui retourne la liste de tous les cookies associés au document sous forme de chaine de caractères ou qui permet de définir un nouveau cookie.
 Quels sont les événements en JQuery? Les événements de Windows? 
 

  
  
