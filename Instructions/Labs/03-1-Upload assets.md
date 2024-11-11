---
lab:
  title: "Labo\_3.1\_: charger des ressources"
---

# Module 3 : gérer les clients et les ressources dans Dynamics 365 Customer Insights - Journeys

## Labo 3.1 : charger des ressources

### Présentation du labo

#### Scénario
Contoso Coffee vend des machines à café professionnelles et grand public à des chefs d’entreprises de café qui utilisent des machines à café Contoso dans leurs magasins, à des entreprises qui ont des machines à café Contoso dans leurs bureaux et à des clients individuels qui utilisent des machines à café Contoso dans leurs habitations. Cette année, la société lance un tout nouveau produit appelé Airpot XL Smart Coffee Machine. Elle prévoit de commercialiser ce nouveau produit pour les entreprises et les particuliers.

L’équipe marketing décide de mettre en place une campagne de vente croisée pour encourager les clients actuels à envisager de changer pour leur nouvelle machine à café intelligente. Ils prévoient d’envoyer une série d’e-mails avec un appel à l’action pour que le client clique sur un lien qui déclenchera un appel téléphonique à un représentant commercial. Ils prévoient de mener cette campagne pendant 2 mois.


Pour cette campagne, le coordinateur marketing devra :
- charger les ressources marketing à utiliser dans les campagnes par e-mail ;
- créer les e-mails marketing à envoyer aux clients ;
- créer le parcours qui automatisera la distribution du contenu de la campagne.

Pour commencer, le coordinateur marketing doit charger les ressources numériques qui seront utilisées dans la campagne. Il doit également charger tous les nouveaux contacts commerciaux que la société a récemment acquis et mettre à jour les détails des contacts et comptes existants.

## Présentation du labo
Ce labo comprend quatre tâches :
1. Dans la première tâche, vous allez charger des fichiers image à utiliser dans les e-mails marketing. Ces fichiers seront chargés dans la bibliothèque des actifs en temps réel.
2. Dans la deuxième tâche, vous allez mettre à jour les détails des contacts existants dans Dynamics 365 Customer Insights - Journeys.
3. Dans la troisième tâche, vous allez créer un modèle de tâche qui sera utilisé dans le parcours.
4. Dans la quatrième tâche, vous allez configurer le profil de marque par défaut à utiliser dans vos ressources marketing (comme les e-mails).

### Ce dont vous avez besoin :
- Un ordinateur ou une machine virtuelle avec un environnement Dynamics 365 Customer Insights - Journeys.
- Les fichiers image à utiliser dans le contenu marketing. Vous pouvez les retrouver dans votre hôte de labo autorisé ou dans le fichier **MB-280T03-Assets.zip** dans le dossier Instructions/Labs/Media du référentiel GitHub. Contactez votre formateur si vous avez des difficultés à les trouver.

### Exercice 1 : préparer les ressources marketing 
## Tâche 1 : charger des images dans la bibliothèque des actifs
1. Téléchargez les fichiers image à partir des documents de ressources. Extrayez les fichiers dans un dossier sur votre bureau.
2. Connectez-vous à Dynamics 365 Customer Insights - Journeys avec vos informations d’identification de l’administrateur.
3. Par défaut, vous devez être dans la zone Parcours en temps réel. Vérifiez que vous êtes dans la zone Parcours en temps réel en ouvrant le sélecteur de zone en bas à gauche de l’écran.
4. Dans le menu de gauche, accédez à la section Actifs. Sélectionnez **Bibliothèque**. Sélectionnez le bouton **+ Nouveau** pour ouvrir la fenêtre de chargement de fichiers.
5. Sélectionnez **+ Ajouter des fichiers**, recherchez les fichiers image sur votre ordinateur local, puis sélectionnez-les.
6. Alors que la fenêtre de chargement est ouverte, ajoutez une balise de logo à contosologo.png. (Commencez par saisir logo dans la zone de texte sous le nom du fichier image. Après avoir saisi *logo*, sélectionnez ce que vous venez de saisir. Une balise est ajoutée sous le nom du fichier.)
7. Sélectionnez **Charger**. Vérifiez que les fichiers image sont chargés. Une coche verte accompagnée de Terminé s’affiche pour chaque fichier. (Le chargement des fichiers peut prendre quelques minutes.) Sélectionnez **Fermer**.
8. À l’aide de la zone de recherche Filtrer par mot clé, entrez *con* et appuyez sur Entrée. Par défaut, ce filtre recherche par nom de fichier. Vérifiez que contosologo.png apparaît dans les résultats de la recherche.

Ces fichiers seront désormais disponibles pour que les utilisateurs puissent les intégrer dans leurs opérations marketing.

### Tâche 2 : mettre à jour les contacts existants
1. Connectez-vous à Dynamics 365 Customer Insights - Journeys. Assurez-vous d’être dans la zone Parcours en temps réel.
2. Dans la navigation de gauche, sélectionnez **Contacts** dans le groupe Audience.
3. Ouvrez le contact **Alva Tharaldsen.**
   - Dans Nom de compte, sélectionnez **Bellows College**. Vous accédez alors à l’enregistrement de compte Bellows College.
   - Faites défiler jusqu’à la sous-grille **Contacts**. Tous les contacts associés à Bellows College sont répertoriés ici. Cliquez sur les points de suspension verticaux en haut de la sous-grille, cliquez sur **Sélectionner** et cochez les cases pour sélectionner tous les contacts de la liste en même temps.
   - En haut de la sous-grille Contacts, sélectionnez les **points de suspension verticaux**. Sélectionnez ensuite **Modifier**.
   - Dans l’onglet Détails, recherchez le champ Notes personnelles. Entrez « Propriétaire d’Airpot » dans le champ. Cliquez sur **Enregistrer**.
   - Sélectionnez l’un des contacts autres qu’Alva. Accédez à l’onglet **Détails**. Vérifiez que « Propriétaire d’Airpot » apparaît dans le champ Notes personnelles.
4. Revenez à l’entité **Contacts** dans le groupe Audience. 
5. Définissez un filtre sur le nom de la société :
   - Sélectionnez la **flèche déroulante** en regard du nom de la société. Sélectionnez **Filtrer par**. Choisissez **Égal à**, puis sélectionnez **Lucerne Publishing, Southridge Video** et **Wingtip Toys**. (Vous pouvez sélectionner les comptes en sélectionnant le nom directement dans la liste, ou en commençant à saisir le nom et en sélectionnant le nom du compte tel qu’il s’affiche.) Sélectionnez **Appliquer**.
   - Sélectionnez tous les contacts pour ces 3 comptes. (Vous pouvez cocher la case en regard du nom complet dans l’en-tête d’affichage pour sélectionner tous les contacts en même temps.)
   - Dans la barre de commandes, sélectionnez **Modifier**. Entrez les informations suivantes :
     - **Adresse 1 : ville :** Bellevue
     - **Adresse 1 : État/province :** Washington
     - **Détails > Notes personnelles :** propriétaire d’Airpot
     - Cliquez sur **Enregistrer**.
6. Modifiez le filtre sur le nom de la société :
   - Sélectionnez la **flèche déroulante** en regard du nom de la société. Sélectionnez **Effacer le filtre**.
   - Sélectionnez à nouveau la **flèche déroulante**. Sélectionnez **Filtrer par**. Sélectionnez **Adatum Corporation** et **Northwind Traders**. Sélectionnez **Appliquer**.
   - Sélectionnez tous les contacts pour ces 2 comptes.
   - Dans la barre de commandes, sélectionnez **Modifier**. Entrez les informations suivantes :
     - **Adresse 1 : ville :** Redmond
     - **Adresse 1 : État/province :** Washington
     - **Détails > Notes personnelles :** propriétaire d’Airpot
     - Cliquez sur **Enregistrer**.
7. Modifiez le filtre sur le nom de la société :
   - Sélectionnez la **flèche déroulante** en regard du nom de la société. Sélectionnez **Effacer des filtres**.
   - Sélectionnez à nouveau la flèche déroulante, puis sélectionnez **Filtrer par**. Sélectionnez **Trey Research**, **The Phone Company** et **Wide World Importers**. Sélectionnez **Appliquer**.
   - Sélectionnez tous les contacts pour ces 3 comptes.
   - Dans la barre de commandes, sélectionnez Modifier. Entrez les informations suivantes :
     - **Adresse 1 : ville :** Seattle
     - **Adresse 1 : État/province :** Washington
     - **Détails > Notes personnelles :** propriétaire d’Airpot
     - Cliquez sur **Enregistrer**.

### Tâche 3 : créer un modèle de tâche
1. Connectez-vous à Dynamics 365 Customer Insights - Journeys avec vos informations d’identification de l’administrateur.
2. Dans le groupe **Ressources**, accédez à **Modèles de tâche**.
3. Cliquez sur **+Nouveau**.
   - Nom : suivi avec le client.
   - Objet :amélioration de la machine à café intelligente d’Airpot à Airpot XL
   - Type de programme : retard (en jours).
   - Retard au début : 0.
4. Dans la section Heure de début, sélectionnez **01** pour l’heure. Laissez la valeur Minute vide.
4. Cliquez sur **Enregistrer et fermer**.

### Exercice 4 : configurer le profil de marque par défaut
1. Connectez-vous à Dynamics 365 Customer Insights - Journeys. Passez à la zone **Paramètres**.
2. Dans le groupe **Engagement client**, accédez à **Profils de marque.**
3. Sélectionnez le **profil de marque par défaut**.
4. Accédez à l’onglet **Expéditeurs**. Vous devez voir l’enregistrement d’expéditeur par défaut dans la sous-grille. 
5. Sélectionnez l’onglet Liens de réseaux sociaux. Renseignez les éléments suivants :
    - URL LinkedIn : https://www.linkedin.com/company/contoso12345/about/
    - URL Twitter : https://twitter.com/ContosoInc
    - URL Facebook : https://www.facebook.com/Contoso-102137176602590/
6. Sélectionnez **Enregistrer et fermer**.

