# Aide utilisateur
## Tutoriel d'utilisation

Le but de l'application est de générer des rapports qui sont la concaténation de plusieurs imports (mails de virement) d'une même banque d'acompte ou de paie.
Il y a quelques étapes à suivre afin de les générer :

- **1ère étape :** La récupération des imports non-traités

  Dans l'onglet de traitement, il suffit de cliquer sur le bouton `traitement` en bas à gauche afin de récupérer tous les mails non-traités et de les afficher dans le tableau juste au-dessus.
  ![etape1](https://user-images.githubusercontent.com/47245748/151384282-f07b4780-2e96-4ff7-901c-1d59b37800c5.png)

- **2ème étape :** La génération des rapports

  Une fois votre liste de mails affichée dans l'onglet de traitement, vous pouvez décider des mails que vous voulez ajoutez dans le rapport en cochant les lignes qui vous intéressent (il est possible de cocher directement la case en haut du tableau pour sélectionner ou déselectionner toutes les lignes) **{1}**. Quand votre choix est fait, vous pourrez enfin lancer la génération du rapport en cliquant sur le bouton `génération` en bas à droite de l'onglet, ce qui aura pour conséquence d'ouvrir la fenêtre erreurs et de vous indiquer combien de rapports vous avez généré **{2}**.
  ![etape2](https://user-images.githubusercontent.com/47245748/151384301-348cf865-6961-42e4-8575-0f88a74b147b.png)

- **3ème étape :** La gestion des rapports

  Vous avez généré des rapports et vous voulez y accéder alors rendez-vous dans l'onglet historique. Vous y trouverez un tableau contenant tous vos rapports que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'un rapport en double-cliquant sur la ligne du rapport souhaité **{1}**. Dans ce rapport, vous aurez accès au bouton `imprimer` qui permet d'ouvrir une prévisualisation d'impression de votre rapport avec le tableau des imports affichée lorsque vous avez appuyé dessus **{3}**. Vous pouvez accéder au dossier de sauvegarde des rapports grâce à l'icône de dossier en haut à droite, à côté du champ `fichier XML` **{2}**.

  ![etape3_1](https://user-images.githubusercontent.com/47245748/151386459-47371b26-7647-490b-83b6-24fa17cbeaba.png)

  ![etape3_23](https://user-images.githubusercontent.com/47245748/151385521-9a456da8-78c7-4a10-98ee-36fb3e8a9e23.png)

## Description des fenêtres de l'application

- **fenêtre principale :**

  Cette fenêtre est le centre de l'application, c'est-à-dire qu'elle permet de tout faire et d'accéder à toutes les fonctionnalités.
  
  Elle est constituée de 3 boutons en haut ainsi que de 5 onglets. 
  Le bouton en haut à gauche permet d'ouvrir la fenêtre d'aide à tout moment et les boutons en haut à droite ouvrent respectivement la fenêtre d'erreur et la fenêtre paramètres.
  Chaque onglet a ces fonctionnalités doc voici un descriptif de chacun :
  
  - **Traitement :**
  
    L'onglet de traitement permet de lancer la génération d'un rapport.
    
    Il contient un bouton `traitement` qui permet de récupérer tous les mails non-traités et de les afficher dans le tableau au-dessus. Une fois votre liste de mails affichée, vous pouvez décider des mails que vous voulez ajoutez dans le rapport en cochant les lignes qui vous intéressent (il est possible de cocher directement la case en haut du tableau pour sélectionner ou déselectionner toutes les lignes). Quand votre choix est fait, vous pourrez enfin lancer la génération du rapport en cliquant sur le bouton `génération` en bas à droite de l'onglet, ce qui aura pour conséquence d'ouvrir la fenêtre erreurs et de vous indiquer combien de rapports vous avez généré.
    
    ![traitement](https://user-images.githubusercontent.com/47245748/151570983-5ccf0c57-b499-4c3e-9887-34ee728097dd.PNG)

  - **Agences :**

    L'onglet agences permet de gérer la base de données des agences.
    
    Il contient un bouton `nouveau` qui permet d'ajouter une nouvelle agence à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de toutes vos agences que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'une agence en double-cliquant sur la ligne de l'agence souhaitée.
    
    ![agences](https://user-images.githubusercontent.com/47245748/151571019-bd034bb6-6c60-41d0-b310-f0dce08a8454.PNG)

  - **Banques :**
  
    L'onglet banques permet de gérer la base de données des banques.
    
    Il contient un bouton `nouveau` qui permet d'ajouter une nouvelle banque à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de toutes vos banques que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'une banque en double-cliquant sur la ligne de la banque souhaitée.
    
    ![banques](https://user-images.githubusercontent.com/47245748/151571044-9dc71aa4-bfcd-4f6b-8923-80f9b30abcf5.PNG)

  - **Intérimaires :**

    L'onglet intérimaires permet de gérer la base de données des intérimaires.
    
    Il contient un bouton `nouveau` qui permet d'ajouter un nouvel intérimaire à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de tous vos intérimaires que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'un intérimaire en double-cliquant sur la ligne de l'intérimaire souhaité.
    
    ![intérimaires](https://user-images.githubusercontent.com/47245748/151572316-919bf931-1930-4b97-9aa4-38d1e6efb556.PNG)

  - **Historique :**

    L'onglet historique permet de consulter vos rapports précédemment générés.
    
    Il contient 3 boutons en bas à droite : un premier bouton `supprimer` qui permet de supprimer le rapport sélectionné dans le tableau au dessus, un bouton `vider l'historique` qui permet de supprimer les anciens rapports ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. L'onglet contient un tableau de tous vos rapports que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'un rapport en double-cliquant sur la ligne du rapport souhaité. Enfin, les deux derniers boutons sont situés en bas à gauche de l'onglet et permettent respectivement de trier le tableau de donnée, au-dessus, par banque et par type de d'import (paies ou acomptes).
    
    ![historique](https://user-images.githubusercontent.com/47245748/151571065-512eced7-e246-42d5-9045-933bca0b904e.PNG)

- **fenêtre descriptif rapport :**

  Cette fenêtre permet de visualiser les données à propos d'un rapport sélectionné.
  
  Elle contient tous les champs d'un rapport ainsi que 2 tableaux situés sur la partie inférieure de la fenêtre qui affiche soit les imports `par agence` contenus dans ce rapport, soit la liste des transactions `par intérimaire` contenues dans ce rapport. Vous pouvez aussi ouvrir le descriptif d'un import, du premier tableau, en double-cliquant sur la ligne de l'import souhaité. Enfin, le bouton `imprimer` permet d'ouvrir une prévisualisation d'impression de votre rapport avec le tableau affichée lorsque vous avez appuyé dessus. Vous pouvez accéder au dossier de sauvegarde des rapports grâce à l'icône de dossier en haut à droite, à côté du champ `fichier XML`.
  
  ![d_rapport](https://user-images.githubusercontent.com/47245748/151571083-74d3eb8a-2567-488b-9ac1-9d39522bcc4b.PNG)

- **fenêtre descriptif import :**

  Cette fenêtre permet de visualiser les données à propos d'un import sélectionné.
  
  Elle contient tous les champs d'un import ainsi qu'une prévisualisation du document PDF lié à l'import en haut à droite de la fenêtre, celle-ci est double-cliquable et affiche le PDF dans un format plus grand et lisible. Vous pouvez aussi voir l'ensemble des transactions liées à cet import dans le tableau situé sur la partie inférieure de la fenêtre.

  ![d_import](https://user-images.githubusercontent.com/47245748/151571336-580c7fce-8572-44ec-9212-34cf225f5c20.PNG)

- **fenêtre descriptif agence :**

  Cette fenêtre permet de visualiser et de modifier vos données d'agence.
  
  Elle contient tous les champs de l'agence qui peuvent être modifiés. Le bouton `valider` permet de valider les modifications apportées et de les enregistrer dans vos données contrairement au bouton `annuler` qui permet de quitter la fenêtre sans sauvegarder vos changements. Enfin, le dernier bouton `supprimer` supprime l'agence de vos données.
  
  ![d_agence](https://user-images.githubusercontent.com/47245748/151571798-98f207b1-4caf-4b8e-969d-e98587478b9f.PNG)
  
- **fenêtre descriptif banque :**

  Cette fenêtre permet de visualiser et de modifier vos données de banque.
  
  Elle contient tous les champs de la banque qui peuvent être modifiés. Le bouton `valider` permet de valider les modifications apportées et de les enregistrer dans vos données contrairement au bouton `annuler` qui permet de quitter la fenêtre sans sauvegarder vos changements. Enfin, le dernier bouton `supprimer` supprime la banque de vos données.
 
  ![d_banques](https://user-images.githubusercontent.com/47245748/151571816-69431301-d28f-46b6-9908-d263807e06a0.PNG)

- **fenêtre descriptif intérimaire :**

  Cette fenêtre permet de visualiser et de modifier vos données d'intérimaire.
  
  Elle contient tous les champs l'intérimaire ainsi que le bouton `supprimer` qui permet de supprimer l'intérimaire de vos données. La fenêtre contient aussi un tableau contenant chaque transaction de votre intérimaire.
  
  ![d_intérim](https://user-images.githubusercontent.com/47245748/151571828-0a88e98e-5f54-4776-85d7-777519752998.PNG)

- **fenêtre paramètres :**

  Cette fenêtre permet de choisir les paramètres de l'application qui sont :
  - Adresse mail générique : permet de donner l'adresse générique pour les tests
  - Adresse mail de retour : permet de choisir si les mails après traitement d'import vont être envoyés aux agences ou à l'adresse générique de test.
  - Ajout des erreurs de doublons : permet d'ajouter ou non les erreurs de boublons aux rapports
  - Ajout des autres erreurs : permet d'ajouter ou non les erreurs (erreurs IBAN, erreurs d'import ...) aux rapports

  ![parametres](https://user-images.githubusercontent.com/47245748/151572062-7571383e-57ef-45c3-a3aa-69b366e5024b.PNG)

- **fenêtre erreurs :**

  Cette fenêtre permet de visualiser les erreurs quotidiennes des rapports.
  
  Elle contient un compteur d'erreur à gauche qui indique le nombre d'erreurs dans les rapports générés ce jour puis 2 tableaux `import` et `intérimaire` qui affiche les lignes erronées de vos rapports. Le bouton `supprimer` permet d'enlever l'erreur sélectionnée dans le tableau afin de cacher les erreurs que vous ne voulez plus voir.
  
  ![erreurs](https://user-images.githubusercontent.com/47245748/151572079-794f8051-79c8-40a2-9a61-b7f0a9522806.PNG)

