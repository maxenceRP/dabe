# Aide développeur
## Explication des Procédures

- **Collection COL_ProcéduresGlobales**
  - Procédure `Connecte_Base_De_Donnée()`
    
    Cette procédure permet d'initialiser notre base de données. On récupère les identifiants contenus dans le fichier INI et on essaye de se connecter au serveur contenant la base de données. En cas de d'échec, on prendra la base locale indiquée dans le fichier INI.
    
  - Procédure `Initialisation_Session()`
  
    Cette procédure permet de récupérer la majorité des éléments contenus dans le fichier INI et initialise la session de réception des imports. Elle renvoie une erreur si certains paramètres ne sont pas présents ou incorrectes.
  
  - Procédure `Vérifie_IBAN(sNuméroIBAN est une chaîne)`
  
    Cette procédure permet de vérifier l'intégrité de la structure de l'IBAN donné en paramètre. 
  
- **Collection COL_Rapport_Agence**
  - Procédure `Envoi_Rapport_Agence(sCodeANA_Agence est une chaîne, sMontantTot est une chaîne)`
  
    Cette procédure permet d'envoyer un mail de confirmation de traitement d'un import soit à l'agence en paramètre soit à l'adresse mail générique en fonction de la valeur de la variable globale gnModeRetour. Cette variable a été récupérée dans le fichier INI.
  
  - Procédure `Fermeture_Email_Rapport()`
  
    Cette procédure permet de fermer la session mail utilisée qui sert à envoyer les mails de confirmation de traitement d'un import.
  
  - Procédure `Ouverture_Email_Rapport()`
  
    Cette procédure permet d'ouvrir la session mail utilisée qui sert à envoyer les mails de confirmation de traitement d'un import.
  
  - Procédure `Redémarre_Session()`
  
    Cette procédure permet de lancer simultanément les deux procédures `Fermeture_Email_Rapport()` et `Ouverture_Email_Rapport()` afin de réinitialiser la session mail.
  
- **Collection COL_XML**
  - Procédure `Ajoute_Groupe_Hdr(sXMLBanque est une chaîne, GroupeNoeud est un xmlNoeud, DateDeTraitement est une chaîne)`
  
    Cette procédure permet d'ajouter au fichier XML de rapport donné en paramètre (`sXMLBanque`) une balise **GrpHdr** en copiant celle du fichier XML d'import donné en paramètre (`GroupeNoeud`). 
  
  - Procédure `Ajoute_Pmt_Inf(sXMLBanque est une chaîne, PmtNoeud est un xmlNoeud, sDateDeTraitement est une chaîne)`
  
    Cette procédure permet d'ajouter au fichier XML de rapport donné en paramètre (`sXMLBanque`) une balise **PmtInf** en copiant celle du fichier XML d'import donné en paramètre (`PmtNoeud`). 
  
  - Procédure `Ajoute_Virement(sXMLBanque est une chaîne, TransactionNoeud est un xmlNoeud)`
  
    Cette procédure permet de créer et d'ajouter au fichier XML de rapport donné en paramètre (`sXMLBanque`) une balise **CdtTrfTxInf** en copiant celle du fichier XML d'import donné en paramètre (`TransactionNoeud`).
  
  - Procédure `Choisir_Rapport(sIBAN_Actuel est une chaîne, bTypeVirement est un booléen)`
  
    Cette procédure permet de choisir dans quel rapport devrait être concaténé un fichier d'import avec comme IBAN de banque `sIBAN_Actuel` et comme type de virement `bTypeVirement`. Si jamais l'import trouve sa place dans un des rapports en train d'être généré, le numéro du rapport est renvoyé, sinon le prochain identifiant de rapport disponible est renvoyé.
  
  - Procédure `Init_XML(FichierXML est un xmlNoeud)`
  
    Cette procédure permet d'attribuer un rapport à chaque import en paramètre (`FichierXML`). Si le rapport n'est pas encore créé alors on va initialiser un nouveau fichier XML et lui ajouter toutes les balises toutes les balises obligatoires grâce aux 3 fonctions `Ajoute ...` . Si jamais le rapport existe déjà, on va update les éléments de celui-ci avec les nouvelles données de l'import.
  
  - Procédure `LectureXML(sFichierXML est une chaîne, sNomAgence est une chaîne, sFichierPDF est une chaîne)`
  
    Cette procédure permet de parcourir le fichier XML d'import et de lancer toutes les autres procédures permettant de concaténer ce fichier avec d'autres dans un rapport en tenant compte des erreurs et des paramètres de l'application.
  
  - Procédure `Sauve_Fichiers_XML()`
  
    Cette procédure permet de sauvegarder les fichiers de rapport précédemment créés.
    
## Explication des Requêtes

- **Requête REQ_Email_Agence_Avec_CodeANA**

  Cette requête permet d'afficher tous les MAIL et Agence tels que Agence.CODE ANA  est égal à 'CodeAgence'.

- **Requête REQ_Erreur_Import**

  Cette requête permet d'afficher tous les IDImport, IDRapport, Statut, CODE ANA, IBANBanque, DateReception, DateTraitement, FichierXML, FichierPDF, NbTransaction, MontantTot, Utilisateur, Type et HashFichierXML  tels que DateTraitement  est supérieur ou égal à 'ParamDateActuelle' ET Statut  est différent de 'valide'.
  
- **Requête REQ_Erreur_Interimaire**

  Cette requête permet d'afficher tous les Nom, IBANInterim, BICInterim, AcompteTotal et Statut  tels que Rapport.DateTraitement  est supérieur ou égal à 'ParamDateActuelle' ET Statut  est différent de 'valide' .
  
- **Requête REQ_MultipleVirement**

  Cette requête permet d'afficher tous les IBANInterim  tels que IBANInterim  est égal à 'IBANInterimaire' ET Import.DateReception  est supérieur ou égal à 'DateReception'.
  
- **Requête REQ_Rapport_Interimaire**

  Cette requête permet d'afficher tous les Nom, IBANInterim, BICInterim, Statut et Montant  tels que Rapport.IDRapport  est égal à ID_du_Rapport.
  
- **Requête REQ_Transactions_Avec_IBANInterim**

  Cette requête permet d'afficher tous les IDTransaction, IDImport, Montant, DateReception et DateTraitement  tels que Transaction.IBANInterim  est égal à 'ParamIBANInterim'.
  

## Description des fenêtres de l'application

- **fenêtre principale :**

  Cette fenêtre est le centre de l'application, c'est-à-dire qu'elle permet de tout faire et d'accéder à toutes les fonctionnalités.
  
  Elle est constituée de 3 boutons en haut ainsi que de 5 onglets. 
  Le bouton en haut à gauche permet d'ouvrir la fenêtre d'aide à tout moment et les boutons en haut à droite ouvrent respectivement la fenêtre d'erreur et la fenêtre paramètres.
  Chaque onglet a ces fonctionnalités doc voici un descriptif de chacun :
  
  - **Traitement :**
  
    L'onglet de traitement permet de lancer la génération d'un rapport.
    
    Il contient un bouton `traitement` qui permet de récupérer tous les mails non-traités et de les afficher dans le tableau au-dessus. Une fois votre liste de mails affichée, vous pouvez décider des mails que vous voulez ajoutez dans le rapport en cochant les lignes qui vous intéressent (il est possible de cocher directement la case en haut du tableau pour sélectionner ou déselectionner toutes les lignes). Quand votre choix est fait, vous pourrez enfin lancer la génération du rapport en cliquant sur le bouton `génération` en bas à droite de l'onglet, ce qui aura pour conséquence d'ouvrir la fenêtre erreurs et de vous indiquer combien de rapports vous avez généré.
    
  - **Agences :**

    L'onglet agences permet de gérer la base de données des agences.
    
    Il contient un bouton `nouveau` qui permet d'ajouter une nouvelle agence à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de toutes vos agences que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'une agence en double-cliquant sur la ligne de l'agence souhaitée.
    
  - **Banques :**
  
    L'onglet banques permet de gérer la base de données des banques.
    
    Il contient un bouton `nouveau` qui permet d'ajouter une nouvelle banque à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de toutes vos banques que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'une banque en double-cliquant sur la ligne de la banque souhaitée.
    
  - **Intérimaires :**

    L'onglet intérimaires permet de gérer la base de données des intérimaires.
    
    Il contient un bouton `nouveau` qui permet d'ajouter un nouvel intérimaire à votre base de données ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. Enfin, l'onglet contient un tableau de tous vos intérimaires que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'un intérimaire en double-cliquant sur la ligne de l'intérimaire souhaité.
    
  - **Historique :**

    L'onglet historique permet de consulter vos rapports précédemment générés.
    
    Il contient 3 boutons en bas à droite : un premier bouton `supprimer` qui permet de supprimer le rapport sélectionné dans le tableau au dessus, un bouton `vider l'historique` qui permet de supprimer les anciens rapports ainsi qu'un bouton `rafraîchir` qui permet de mettre à jour la table de donnée au-dessus. L'onglet contient un tableau de tous vos rapports que vous pouvez trier en cliquant sur le haut des colonnes, vous pouvez aussi ouvrir le descriptif d'un rapport en double-cliquant sur la ligne du rapport souhaité. Enfin, les deux derniers boutons sont situés en bas à gauche de l'onglet et permettent respectivement de trier le tableau de donnée, au-dessus, par banque et par type de d'import (paies ou acomptes).

- **fenêtre descriptif rapport :**

  Cette fenêtre permet de visualiser les données à propos d'un rapport sélectionné.
  
  Elle contient tous les champs d'un rapport ainsi que 2 tableaux situés sur la partie inférieure de la fenêtre qui affiche soit les imports `par agence` contenus dans ce rapport, soit la liste des transactions `par intérimaire` contenues dans ce rapport. Vous pouvez aussi ouvrir le descriptif d'un import, du premier tableau, en double-cliquant sur la ligne de l'import souhaité. Enfin, le bouton `imprimer` permet d'ouvrir une prévisualisation d'impression de votre rapport avec le tableau affichée lorsque vous avez appuyé dessus. Vous pouvez accéder au dossier de sauvegarde des rapports grâce à l'icône de dossier en haut à droite, à côté du champ `fichier XML`.
  
- **fenêtre descriptif import :**

  Cette fenêtre permet de visualiser les données à propos d'un import sélectionné.
  
  Elle contient tous les champs d'un import ainsi qu'une prévisualisation du document PDF lié à l'import en haut à droite de la fenêtre, celle-ci est double-cliquable et affiche le PDF dans un format plus grand et lisible. Vous pouvez aussi voir l'ensemble des transactions liées à cet import dans le tableau situé sur la partie inférieure de la fenêtre.

- **fenêtre descriptif agence :**

  Cette fenêtre permet de visualiser et de modifier vos données d'agence.
  
  Elle contient tous les champs de l'agence qui peuvent être modifiés. Le bouton `valider` permet de valider les modifications apportées et de les enregistrer dans vos données contrairement au bouton `annuler` qui permet de quitter la fenêtre sans sauvegarder vos changements. Enfin, le dernier bouton `supprimer` supprime l'agence de vos données.
  
- **fenêtre descriptif banque :**

  Cette fenêtre permet de visualiser et de modifier vos données de banque.
  
  Elle contient tous les champs de la banque qui peuvent être modifiés. Le bouton `valider` permet de valider les modifications apportées et de les enregistrer dans vos données contrairement au bouton `annuler` qui permet de quitter la fenêtre sans sauvegarder vos changements. Enfin, le dernier bouton `supprimer` supprime la banque de vos données.
 
- **fenêtre descriptif intérimaire :**

  Cette fenêtre permet de visualiser et de modifier vos données d'intérimaire.
  
  Elle contient tous les champs l'intérimaire ainsi que le bouton `supprimer` qui permet de supprimer l'intérimaire de vos données. La fenêtre contient aussi un tableau contenant chaque transaction de votre intérimaire.
  
- **fenêtre paramètres :**

  Cette fenêtre permet de choisir les paramètres de l'application qui sont :
  - Adresse mail générique : permet de donner l'adresse générique pour les tests
  - Adresse mail de retour : permet de choisir si les mails après traitement d'import vont être envoyés aux agences ou à l'adresse générique de test.
  - Ajout des erreurs de doublons : permet d'ajouter ou non les erreurs de boublons aux rapports
  - Ajout des autres erreurs : permet d'ajouter ou non les erreurs (erreurs IBAN, erreurs d'import ...) aux rapports

- **fenêtre erreurs :**

  Cette fenêtre permet de visualiser les erreurs quotidiennes des rapports.
  
  Elle contient un compteur d'erreur à gauche qui indique le nombre d'erreurs dans les rapports générés ce jour puis 2 tableaux `import` et `intérimaire` qui affiche les lignes erronées de vos rapports. Le bouton `supprimer` permet d'enlever l'erreur sélectionnée dans le tableau afin de cacher les erreurs que vous ne voulez plus voir.
