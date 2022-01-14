# Aide

## Description des fenêtres de l'application:

- **fenêtre principale :**

  Cette fenêtre est le centre de l'application, c'est-à-dire qu'elle permet de tout faire et d'accéder à toutes les fonctionnalités.
  
  Elle est constituée de 3 boutons en haut ainsi que de 5 onglets. 
  Le bouton en haut à gauche permet d'ouvrir la fenêtre d'aide à tout moment et les boutons en haut à droite ouvrent respectivement la fenêtre d'erreur et la fenêtre paramètres.
  Chaque onglet a ces fonctionnalités doc voici un descriptif de chacun :
  
  - Traitement :
  
    L'onglet de traitement permet de lancer la génération d'un rapport.
    
    Il contient un bouton `traitement` qui permet de récupérer tous les mails non-traités et de les afficher dans le tableau au-dessus. Une fois votre liste de mails affichée, vous pouvez décider des mails que vous voulez ajoutez dans le rapport en cochant les lignes qui vous intéressent (il est possible de cocher directement la case en haut du tableau pour sélectionner ou déselectionner toutes les lignes). Quand votre choix est fait, vous pourrez enfin lancer la génération du rapport en cliquant sur le bouton `génération` en bas à droite de l'onglet, ce qui aura pour conséquence d'ouvrir la fenêtre erreurs et de vous indiquer combien de rapports vous avez généré.
    
  - Agences :

    L'onglet agences permet de gérer la base de données des agences.
    
    Il contient un bouton `nouveau` qui permet d'ajouter une nouvelle agence à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de toutes vos agences que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'une agence en double-cliquant sur la ligne de l'agence souhaitée.
    
  - Banques :
  
    L'onglet banques permet de gérer la base de données des banques.
    
    Il contient un bouton `nouveau` qui permet d'ajouter une nouvelle banque à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de toutes vos banques que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'une banque en double-cliquant sur la ligne de la banque souhaitée.
    
  - Intérimaires :

    L'onglet intérimaires permet de gérer la base de données des intérimaires.
    
    Il contient un bouton `nouveau` qui permet d'ajouter un nouvel intérimaire à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de tous vos intérimaires que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'un intérimaire en double-cliquant sur la ligne de l'intérimaire souhaité.
    
  - Historique :

    L'onglet historique permet de consulter vos rapports précédemment générés.
    
    Il contient 2 boutons en bas à droite : un bouton `vider l'historique` qui permet de supprimer les anciens rapports ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. L'onglet contient un tableau de tous vos rapports que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'un rapport en double-cliquant sur la ligne du rapport souhaité. Enfin, les deux derniers boutons sont situés en bas à gauche de l'onglet et permettent respectivement de trier le tableau de donnée, au-dessus, par banque et par type de d'import (paies ou acomptes).

- **fenêtre descriptif rapport :**
- **fenêtre descriptif import :**
- **fenêtre descriptif transaction :**


- **fenêtre descriptif agence :**

  Cette fenêtre permet de visualiser et de modifier vos données d'agence.
  
  Elle contient tous les champs de l'agence qui peuvent être modifiés. Le bouton `valider` permet de valider les modifications apportées et de les enregistrer dans vos données contrairement au bouton `annuler` qui permet de quitter la fenêtre sans sauvegarder vos changements. Enfin, le dernier bouton `supprimer` supprime l'agence de vos données.
  
- **fenêtre descriptif banque :**

  Cette fenêtre permet de visualiser et de modifier vos données de banque.
  
  Elle contient tous les champs de la banque qui peuvent être modifiés. Le bouton `valider` permet de valider les modifications apportées et de les enregistrer dans vos données contrairement au bouton `annuler` qui permet de quitter la fenêtre sans sauvegarder vos changements. Enfin, le dernier bouton `supprimer` supprime la banque de vos données.
 
- **fenêtre descriptif intérimaire :**

  Cette fenêtre permet de visualiser et de modifier vos données d'intérimaire.
  
  Elle contient tous les champs l'intérimaire ainsi que le bouton `supprimer` qui permet de supprimer l'intérimaire de vos données. La fenetre contient aussi un tableau contenant chaque transaction de votre intérimaire.
  
- **fenêtre paramètres :**

  Cette fenêtre permet de choisir les paramètres de l'application qui sont :
  - Adresse mail générique : permet de donner l'adresse générique pour les tests
  - Adresse mail de retour : permet de choisir si les mails envoyés apres traitement d'import vont être envoyé aux agences ou à l'adresse générique de test.
  - Ajout des erreurs de banque : permet d'ajouter ou non les erreurs (doublons, erreur IBAN, ...) au rapports

- **fenètre erreurs :**

  Cette fenêtre permet de visualiser les erreurs quotidiennes des rapport.
  
  Elle contient un compteur d'erreur à gauche qui indeque le nombre d'erreurs dans les rapports générés ce jour puis deux tableau `import` et `intérimaire` qui affiche les lignes erronnées de vos rapports. Le bouton `supprimer` permet d'enlever l'erreur selectionnée dans le tableau afin de cacher les erreurs que vous ne voulez plus voir.
