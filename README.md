# Design-patterns
un projet maven qui implémente 2 design patterns :Singleton et Strategy
Le projet design-patterns implémente des exemples basiques de design patterns.

Les design patterns sont des solutions aux problèmes récurrents; des directives sur la manière de traiter certains problèmes. Ce ne sont pas des classes, des packages ou des bibliothèques que vous pouvez connecter à votre application et attendez que la magie se produise. Ce sont plutôt des directives sur la façon de résoudre certains problèmes dans certaines situations.

     Design pattern = description / modèle permettant de résoudre un problème pouvant être utilisé dans de nombreuses situations différentes.
     
Ce projet contient 2 types de design patterns : 
                                           - design pattern singleton 
                                           - design pattern strategy
                                           

Le design pattern singleton:
L’objectif du pattern SINGLETON est de garantir qu’une classe ne possède qu’une seule instance et de fournir un point d’accès global à celle-ci. Le pattern SINGLETON est placé dans la catégorie "patterns de création".

Le design pattern strategy:
L’objectif du pattern STRATEGY est d’encapsuler des approches, ou stratégies, alternatives dans des classes distinctes qui implémentent chacune une opération commune

La structure générale du projet :
-	src :
       -main -->java -->com--> amina--> org--> design--> patterns-->singleton-->  DatabasConnectionSIG.java
                                                                  --> strategy-->AmazonBoughtItems.java
                                                                              -->cards-->CardOperator.java
								                                                                      -->MasterCard.java
								                                                                      -->PaypalCard.jav

     -test-->java -->com--> amina--> org--> design--> patterns-->singleton-->  DatabasConnectionSIGTest.java
				                              -->strategy-->AmazonBoughtItemsTest.java
     - target
     - pom.xml

Points à noter:

- DatabasConnectionSIG.java:
C’est la classe qui implémente le design pattern singelton ; c’est une classe qui permet la connexion à une base de données et cette connexion doit être unique.
           Création du singleton :
              1-	Le constructeur DatabasConnectionSIG()doit être privé
              2-	Créer un attribut onlyInstance privé statique qui contient un seul objet de type DatabasConnectionSIG
              3-	Créer une méthode getInstance() statique qui retourne l’attribut statique

- AmazonBoughtItems.java:
C’est la classe qui implémente le design pattern singelton ; cette technique est utilisée dans l’exemple de paiement avec carte bancaire
      -On définit l’interface CardOperator.java avec la méthode abstraite getNameCard() ; c’est la classe générique de la stratégie 
      - Les classes   MasterCard.java et PaypalCard.java implémente l’interface et redéfinissent la fonction.
      - La classe AmazonBoughtItems.java utilise un objet de l’interface et définit des méthodes de paiement.
      
- DatabasConnectionSIGTest.java et AmazonBoughtItemsTest.java: 
ce sont des classes de test de Junit qui utilise les annotations pour identifier les méthodes test.

- fichier pom.xml : 
il définit une seule dépendance ; c’est la dépendance du test Junit
