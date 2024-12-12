---
lab:
  title: "Lab\_3.2\_: créer un e-mail"
---

# Parcours d’apprentissage 3 : gérer les clients et les ressources dans Dynamics 365 Customer Insights - Journeys

## Lab 3.2 : créer un e-mail

### Présentation du labo

#### Scénario
Pour cette campagne, l’équipe marketing prévoit de faire un grand blitz autour de sa plus récente machine à café intelligente. Ils prévoient d’envoyer une série de trois e-mails. Le premier e-mail promouvoira la machine à café intelligente de Contoso. Le deuxième e-mail est destiné à encourager les propriétaires de l’airpot standard à mettre à niveau vers la nouvelle machine intelligente. Le troisième e-mail est un rappel sur le lancement du nouveau produit. 

### Présentation du labo
Ce laboratoire comprend trois exercices :
1. Dans cet exercice, vous allez créer un e-mail à l’aide d’un modèle de messagerie.
2. Dans cet exercice, vous allez créer un e-mail en copiant un autre e-mail.
3. Dans cet exercice, vous allez créer un e-mail en copiant un autre e-mail.

### Ce dont vous avez besoin :
- Un ordinateur avec un environnement Dynamics 365 Customer Insights - Journeys.

## Exercice : créer une page marketing
### Tâche 1 : créer un modèle d’e-mail
1. Connectez-vous à Dynamics 365 Customer Insights - Journeys. Assurez-vous d’être dans la zone Parcours en temps réel.
2. Accédez aux **e-mails** sous le groupe Canaux.
3. Cliquez sur **+Nouveau** pour créer un nouvel événement.
4. Dans la galerie de modèles, faites défiler jusqu’à la **section Dispositions** . Sélectionnez **la colonne** 1-2 et **sélectionnez.**
5. Dans le coin supérieur gauche, remplacez le nom de l’e-mail par e-mail par e-mail *de la campagne Smart Machine 1**.* (Lorsque vous pointez sur le pointage **E-mail 1** dans le coin supérieur gauche, vous devez être en mesure de taper dans cette zone de texte.)
6. Sélectionnez la **zone** Nom/Objet dans le concepteur pour afficher les détails de l’en-tête e-mail.
   - Tapez ce qui suit dans le sujet : « Enfin, une machine à café qui m’obtient ».
   - Sélectionnez **Contoso Coffee** comme expéditeur (si ce n’est pas déjà le cas). Le nom de l’adresse de départ et l’e-mail De doivent être renseignés et doivent être en lecture seule.
7. Recherchez le **menu Boîte à outils** à l’extrême droite, qui s’affiche sous la forme d’une série d’icônes. Le pointage sur les icônes affiche le nom de chaque onglet. Sélectionnez l’onglet **Thème** , qui ressemble à un pinceau.
   - **Remarque :** les détails de cette section affectent l’intégralité de l’e-mail. Si vous ajoutez de nouveaux éléments de texte à l’e-mail, la police, la taille et la couleur sont répertoriées ici par défaut. Vous pouvez ensuite mettre à jour ces éléments en fonction des besoins.
   - Remplacez la Famille de polices par Segoe UI.
   - Remplacez la Couleur du corps de texte par #404040.
   - Remplacez l’arrière-plan de l’e-mail **** par : #CCCCCC.
8. Dans l’e-mail lui-même, recherchez la première section et sélectionnez-la. Un onglet Modifier la disposition s’affiche. Remplacez la couleur d’arrière-plan section par une nuance de gris.

## Tâche 2 : Mettre à jour des images
Dans cette tâche, nous allons mettre à jour le logo.

1. Sélectionnez l’image dans la première section du concepteur.
2. Sur la droite, cliquez sur l’image d’espace réservé. Sélectionnez **Remplacer l’image** , puis choisissez **Parcourir la bibliothèque.**
3. Sélectionnez le **logo** Contoso, puis cliquez sur **Sélectionner.**
4. Remplacez le texte de remplacement par *le logo* Contoso.
5. Sélectionnez le **lien pour** la liste déroulante, puis sélectionnez **URL**. Entrez *www.contoso.com.*
6. Dans la section Taille et alignement, si la largeur automatique est activée, utilisez le bouton bascule pour le désactiver. Entrez *150 px* pour la largeur. L’autre dimension sera automatiquement mise à jour.
7. Ensuite, nous allons mettre à jour la deuxième image dans l’e-mail. Sélectionnez l’image dans la section située sous le logo.
8. Sélectionnez **Remplacer l’image** et **parcourir la bibliothèque.**
9. Sélectionnez l’image **hero-page.jpg** . Cliquez sur **Sélectionner**.

## Tâche 3 : Mettre à jour un titre à l’aide de la personnalisation
Dans cette tâche, nous allons mettre à jour un titre pour refléter le prénom du contact du destinataire.
1. Accédez à la section de texte sous le logo et sélectionnez-la.
2. Placez votre curseur au début du texte d’en-tête, puis cliquez sur **Personnalisation** dans la barre d’outils en haut de l’e-mail. Sélectionnez **Nom** dans le menu déroulant. Vérifiez que **le contact** est sélectionné et sélectionnez **Choisir.**
3. Ajoutez une virgule et un espace après {{Firstname}}.
4. Remplacez le texte de l’espace réservé par : « Nous avons couvert vos pauses café ».
5. Mettez en surbrillance le texte, mettez-le en gras et remplacez la taille *de police par 26.*
6. Modifier « Personnaliser votre e-mail... » « La nouvelle machine à café intelligente Airpot XL est comme avoir votre propre barista personnel. »
7. Mettez en surbrillance le texte, puis définissez sa taille sur *24*.

## Tâche 4 : Concevoir le reste de l’e-mail
1. Sélectionnez la section à deux colonnes sous le texte. Remplacez la couleur d’arrière-plan section par une nuance de bleu.
2. Dans la colonne de gauche, sélectionnez l’espace réservé Image, puis cliquez sur **Remplacer l’image.** Sélectionnez **Parcourir la bibliothèque** et sélectionnez **coffee-machine.jpg.** Cliquez sur **Sélectionner**.
3. Remplacez le texte de remplacement par « Machine à café ». (Si le volet pour modifier l’image ne s’affiche pas immédiatement, vous pouvez trouver les propriétés de l’image en tant qu’icône inférieure dans l’icône **Menu Boîte à outils** .)
4. Dans **Lien vers** le champ, sélectionnez **l’URL.** Saisissez https://dynamics.microsoft.com/.
5. Dans la section Taille et alignement, désactivez la largeur **automatique.** Remplacez la largeur par *150 px* et laissez l’autre dimension définie automatiquement.
6. Dans la colonne de droite sous l’en-tête, sélectionnez l’espace réservé Image, puis cliquez sur **Remplacer l’image.** Sélectionnez **Parcourir la bibliothèque** et sélectionnez **barista.jpg**. Cliquez sur **Sélectionner**.
7. Remplacez le texte de remplacement par *Barista.*
8. Dans Lien vers le champ, sélectionnez l’URL. Saisissez https://dynamics.microsoft.com/.
9.  Sélectionnez la section avec les icônes sociales. Remplacez la couleur d’arrière-plan section par une nuance de gris.
10. Sélectionnez la section avec les informations sur le droit d’auteur. Mettez à jour le copyright de *2022 Company Inc.* à *2024 Contoso Coffee.*
11. Apportez d’autres modifications comme vous le souhaitez. N’hésitez pas à être créatif et à utiliser n’importe quelle expérience de conception que vous avez. Qu’est-ce que vous trouvez accrocheur lors de la réception d’un e-mail marketing ?

## Tâche 5 : Enregistrer et tester l’e-mail
16. Cliquez sur **Save** dans la barre d'outils.
17. Sélectionnez **Aperçu et test.**
18. Sélectionnez **Exemple de données**. Dans le volet de personnalisation d’aperçu, entrez le prénom d’un contact que vous avez créé. Sélectionnez le contact pour surveiller la modification de personnalisation.
19. Revenez à l’écran **Aperçu et test** . Affichez un aperçu de l’e-mail sur toutes les tailles d’écran.
20. Cliquez sur la flèche Suivant pour continuer. Exécutez le **vérificateur** d’accessibilité pour voir s’il existe d’autres problèmes dans l’e-mail. Réduisez les autres problèmes à mesure que vous le voyez.
21. Dans la barre d’outils, cliquez sur **Prêt à envoyer.**

### Exercice 2 : Créer un e-mail en copiant un e-mail

## Tâche 1 : Créer un e-mail aux clients existants
1. Connectez-vous à Dynamics 365 Customer Insights - Journeys. Assurez-vous d’être dans la zone Parcours en temps réel.
2. Accédez aux **e-mails** sous le groupe Canaux.
3. Ouvrez l’e-mail que vous avez créé dans la tâche 1.
4. Dans la barre de commandes, cliquez sur la **flèche** déroulante en regard de Enregistrer. Choisissez **Enregistrer sous.**
5. Dans le menu Création rapide à droite, nommez l’e-mail *Upgrade Airpot Email.*
6. Dans le champ Objet, entrez « Est-il temps pour une mise à niveau ? »
7. Cliquez sur **Enregistrer et fermer**. Une fenêtre contextuelle s’affiche indiquant que *vos modifications ont été enregistrées*. Cliquez sur **Afficher l’enregistrement** pour ouvrir le nouvel e-mail. (Vous pouvez également revenir à **E-mails et e-mails** de **mise à niveau airpot.**)
8. Dans le concepteur, remplacez le texte d’en-tête par « {{Firstname}}, caféez votre chemin, à portée de main ».
9. Remplacez la copie sous l’en-tête par : « Votre commande de café est aussi unique que vous le faites. Il est temps d’essayer notre nouvelle machine à café intelligente Airpot.
10. Sélectionnez la section à deux colonnes suivante. Remplacez le panneau de disposition  par .
    - Dans la colonne de gauche, effectuez les mises à jour suivantes :
      - Supprimer l’outil
      - Supprimez le bouton
    - Dans la colonne de droite, effectuez les mises à jour suivantes :
      - Retirer l’image
      - Remplacez le texte par : « Demi-caf Americano, ou double coup de latte ? Toutefois, vous choisissez de alimenter votre journée, Contoso Coffee vous a couvert. » ‎ 
      - Remplacez la taille de police par 16 et italique.
11. Bouton Mettre à jour le niveau
    - Sélectionnez le bouton .
    - Modifiez le lien vers l’URL.
    - Saisissez https://dynamics.microsoft.com/.
    - Modifiez le texte du bouton pour *EXPLORER LA NOUVELLE MACHINE INTELLIGENTE.*
    - Développez **La taille et l’alignement.** Basculez vers le texte désactivé **.** Changez la largeur sur 10 px.
12. Cliquez sur **Save** dans la barre d'outils.
13. Aperçu du courrier électronique.
14. cliquez alors sur Extraire. Corrigez les erreurs si nécessaire.
15. Dans la barre d’outils, cliquez sur **Prêt à envoyer.**

### Tâche 2 : Créer un e-mail de campagne de suivi
1. Connectez-vous à Dynamics 365 Customer Insights - Journeys. Assurez-vous d’être dans la zone Parcours en temps réel.
2. Accédez aux **e-mails** sous le groupe Canaux.
3. Ouvrez l’e-mail que vous avez créé dans la tâche 2.
4. Dans la barre de commandes, cliquez sur la flèche déroulante en regard de **Enregistrer**. Choisissez **Enregistrer sous.**
5. Dans le menu Création rapide à droite, nommez le rappel de campagne Smart Machine par e-mail *.*
6. Dans le champ Objet, entrez « Avez-vous vu les actualités ? »
7. Cliquez sur **Enregistrer et fermer**. Une fenêtre contextuelle s’affiche en haut à droite, indiquant que vos modifications ont été enregistrées. Cliquez sur **Afficher l’enregistrement** pour ouvrir le nouvel e-mail. (Vous pouvez également accéder à la liste e-mails et ouvrir **Rappel** de campagne Smart Machine.)
8. Remplacez le texte de l’en-tête par : « La nouvelle machine intelligente Airpot : disponible cette automne ! »
9. Remplacez la copie sous l’en-tête par : « Notre nouvelle machine intelligente Airpot est une nouvelle façon de faire du café. Apprenez-en davantage sur la première machine à café de son genre aujourd’hui.
10. Supprimez la section à deux colonnes.
11. Cliquez sur **Save** dans la barre d'outils.
12. Aperçu du courrier électronique.
13. cliquez alors sur Extraire. Corrigez les erreurs si nécessaire.
14. Dans la barre d’outils, cliquez sur **Prêt à envoyer.**

