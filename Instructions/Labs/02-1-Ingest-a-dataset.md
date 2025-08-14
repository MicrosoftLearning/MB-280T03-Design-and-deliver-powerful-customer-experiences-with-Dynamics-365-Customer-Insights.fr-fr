---
lab:
  title: "Labo\_2.1\_: ingérer un jeu de données"
---

# Module 2 : ingérer des données dans Dynamics 365 Customer Insights - Data

## Scénario de labo : Contoso Coffee
La société Contoso Coffee produit du café et des machines à café de haute qualité qu’elle vend par différents canaux dont les nouveaux magasins Contoso situés dans des emplacements stratégiques, les épiceries fines et sur le site web Contoso Coffee. Contoso prévoit d’élargir son offre avec Contoso Cafés et une nouvelle machine à café connectée, capable de déclencher le remplissage d’une nouvelle boisson et d’alerter le service Contoso en cas de problème. Cette nouvelle offre lui permettra d’établir des relations directes avec ses clients et de développer sa connaissance de leurs besoins.

### Problématiques de Contoso Coffee
- **Relation transactionnelle :** leur modèle économique existant signifie qu’ils n’ont pas de relation directe avec leurs clients.
- **Silos de données :** la société n’est pas en mesure d’offrir des expériences client personnalisées.

### Paysage de données existant de Contoso
- **Données client fragmentées :** avec plusieurs systèmes, Contoso a plusieurs enregistrements pour la même personne. Cela entraîne une expérience incohérentes pour le client qui s’attend à être traité comme une seule personne, quel que soit le canal sur lequel il effectue des transactions.
- **Plateformes multiples :** l’architecture de Contoso a évolué par le biais d’acquisitions et de systèmes hérités, ce qui signifie que les données peuvent résider non seulement dans différents systèmes, mais sur plusieurs plateformes sur plusieurs clouds et sur site.
- **Données non client :** Contoso établit des corrélations entre les données non client et l’impact qu’elles ont sur les expériences client, y compris les données provenant de tiers tels que les données météorologiques.

### Projet Customer Insights de Contoso Coffee
Vous avez été sélectionné comme chef de projet pour la mise en œuvre de Dynamics 365 Customer Insights chez Contoso Coffees. En tant que chef de projet expérimenté, vous élaborez le plan suivant :
1. Créer un environnement Customer Insights
2. Ingérer des données à partir de sources de données de la plus haute priorité dans l’entreprise :
   - Point de vente (PDV)
   - Données de fidélité
   - Clients e-commerce
   - Achats web
3. Créer un profil client unifié à partir des données ingérées.

## Présentation du module

### Prérequis du labo :
Avant de commencer cet exercice, vous devez avoir terminé le labo 0 pour configurer votre environnement.

### Ingestion des données et unification des données
En tant que chef de projet pour Contoso Retail, vous allez créer un profil client unifié en ingérant des sources clés de données client et en suivant le processus de mappage, de correspondance et de fusion. Dans ce labo, nous allons ingérer des données. Dans le labo suivant, nous allons unifier les données.

**Durée estimée :** 45 minutes

### Familiarisation avec Customer Insights - Data
Dans cette tâche, vous allez explorer l’environnement de démonstration préconfiguré pour vous familiariser avec l’application Customer Insights - Data.
1. Connectez-vous à Customer Insights - Data sur https://home.ci.ai.dynamics.com si ce n’est pas déjà le cas.
2. Dans le sélecteur d’environnement dans le coin supérieur droit, vérifiez que l’**essai marketing** est sélectionné.
3. Explorez les options de menu de gauche pour vous familiariser avec la navigation :
   - **Accueil :** page d’accueil
   - **Clients :** afficher les cartes pour les profils client unifiés (vous ne pourrez pas encore voir cela, nous devons d’abord ingérer et unifier nos données)
   - **Données > Sources de données :** ingérer des données démographiques, transactionnelles ou comportementales en silo. Effectuez des mappages, des correspondances et des fusions dans un profil client unifié. Affichez vos entités et définissez les types d’activités et leurs relations avec vos clients.
   - **Données > Enrichissement :** aller au delà de votre profil unifié et enrichir les profils clients avec les données propriétaires Microsoft. Déverrouillez des données sur les affinités de centaines de marques et de dizaines de catégories d’intérêt. Ces affinités sont extraites pour des profils susceptibles d’être similaires à vos clients.
   - **Insights > Segments, mesures et prédictions :** afficher des segments, configurer des mesures et utiliser des modèles de prédiction prêts à l’emploi (ou créer vos propres modèles). (Vous ne pourrez pas encore afficher cette section.)
   - **Paramètres** : administrer les rôles, les autorisations, les API, et les destinations d’exportation pour les segments client.

## Exercice 1 : ingestion des données
Dans ce labo, vous allez vous familiariser avec l’ingestion de données provenant de plusieurs sources. En tant que chef de projet chez Contoso Retail, vous avez déjà identifié que les principales sources de données incluent les clients e-commerce, les achats en ligne, les achats au niveau des points de vente en magasin et les données du programme de cartes de fidélité Contoso Retail.

### Tâche 1 : ingérer les données client à partir d’une plateforme d’e-commerce
1. Connectez-vous à Client Insights sur http://home.ci.ai.dynamics.com, et vérifiez que la **version d’évaluation marketing** est sélectionnée dans le menu déroulant dans le coin supérieur droit.
2. Dans Customer Insights, développez **Données** dans le menu de navigation de gauche et sélectionnez **Source de données**.
3. Sélectionnez **+Ajouter une source de données**. Affichez les méthodes disponibles pour ingérer des données. Pour ce labo, choisissez Microsoft Power Query, nommez la source * e-commerce*, puis sélectionnez **Suivant**.
4. Une vue des sources de données Power Query que Customer Insights est capable d’ingérer s’affiche. Notez les types de connecteurs disponibles. Sélectionnez le connecteur **Texte/CSV**.
5. Entrez https://aka.ms/CI-ILT/Contacts pour le chemin d’accès ou l’URL du fichier, puis sélectionnez **Suivant**. Le chargement des données peut prendre plusieurs minutes.
6. Vous devriez maintenant voir les données de la source tabulées. Sélectionnez **Transformer des données** pour configurer les types et formats de données pour les données que vous ingérer.
7. Vous noterez que l’en-tête de colonne apparaît dans la première ligne des données. Pour corriger ce problème, dans l’onglet Accueil, sélectionnez **Transformer > Utiliser la première ligne comme en-têtes** ou sélectionnez l’onglet **Transformer**, puis **Utiliser la première ligne comme en-têtes**.
8. Étant donné que nous avons ingéré des données à partir d’une source Texte/CSV, toutes les colonnes ont par défaut un type de données « Texte ». Pour réussir l’ingestion et la modélisation des données, nous pouvons définir le type de données pour les colonnes non textuelles. Pour modifier le type de données, sélectionnez l’icône ABC dans l’en-tête de chaque colonne. Mettez à jour le type de données de ces colonnes :
   - **DateOfBirth** : date
   - **CreatedOn** : date
   - **Income :** devise
9. Vérifiez que le champ Nom dans le volet Paramètres de requête est défini sur Contacts. Cliquez sur **Suivant**. Cliquez sur **Enregistrer**.
   - Félicitations ! Vous avez maintenant créé votre première source de données avec un jeu de données ! Nous allons continuer à importer le jeu de données suivant dans la tâche suivante.

## Tâche 2 : ingérer les données d’achat en ligne
Dans cette nouvelle tâche, nous allons ingérer les données d’achat en ligne, qui représentent les achats effectués sur le site web de Contoso Coffee.

1. Dans Customer Insights, développez **Données** dans le menu de gauche et sélectionnez **Source de données**.
2. Dans *Géré par moi (1)*, sélectionnez le jeu de données **e-commerce**, puis sélectionnez **Modifier**. Cliquez sur **Suivant**.
   - **Note :** si vos données sont toujours en cours d’actualisation, attendez que cette opération soit terminée avant de les modifier. Vous pouvez passer directement à la tâche 3, puis revenir à la tâche 2 une fois que vous avez terminé les tâches 3 à 5.
3. Une vue Power Query des données des contacts e-commerce que vous avez ingérées lors de la tâche 1 devrait s’afficher. Dans l’onglet **Accueil**, sélectionnez **Obtenir des données**.
4. Une vue des connecteurs de source de données que Customer Insights est capable d’ingérer s’affiche. Sélectionnez le connecteur **Texte/CSV**.
5. Entrez https://aka.ms/CI-ILT/OnlinePurchases pour le chemin d’accès ou l’URL du fichier, puis sélectionnez **Suivant**. Sélectionnez **Créer**.
6. Comme précédemment, sélectionnez **Transformer**, puis **Utiliser la première ligne comme en-têtes**.
7. Mettez à jour les types de données pour les colonnes suivantes :
   - **PurchasedOn** : date
   - **TotalPrice** : devise
8. Nommez cette requête *Achats*, puis sélectionnez **Enregistrer**.

## Tâche 3 : ingérer les données client du programme de fidélité
1. Dans Customer Insights, développez **Données** dans le menu de gauche et sélectionnez **Source de données**.
2. Sélectionnez **+Ajouter une source de données** et choisissez **Microsoft Power Query** comme méthode d’importation. Nommez la source *Fidélité*, puis sélectionnez **Suivant**.
3. Sélectionnez le connecteur **Texte/CSV**.
4. Entrez https://aka.ms/CI-ILT/LoyaltySchemeCustomers pour le chemin d’accès ou l’URL du fichier, sélectionnez **Suivant**, puis **Transformer les données**.
5. Comme précédemment, sélectionnez Transformer, puis Utiliser la première ligne comme en-têtes.
6. Mettez à jour le type de données de ces colonnes :
   - **DateOfBirth** : date
   - **RewardsPoints** : nombre entier
   - **CreatedOn** : date
7. Renommez cette requête en *Clients* dans le volet Paramètres de requête, puis sélectionnez **Suivant**.
8. Dans l’écran d’actualisation, sélectionnez **Enregistrer**.

## Tâche 4 : ingérer des données client à partir des achats en point de vente
1. Dans Customer Insights, développez **Données** dans le menu de navigation de gauche et sélectionnez **Source de données**.
2. Sélectionnez **+ Ajouter une source de données**, choisissez **Microsoft Power Query** et nommez la source *PDV*, puis sélectionnez **Suivant**.
3. Sélectionnez le connecteur **Texte/CSV**.
4. Entrez https://aka.ms/CI-ILT/POSPurchases pour le chemin d’accès ou l’URL du fichier. Sélectionnez **Suivant**, puis **Transformer les données**.
5. Comme précédemment, sélectionnez **Transformer**, puis **Utiliser la première ligne comme en-têtes**.
6. Mettez à jour le type de données de ces colonnes :
   - **PurchasedOn** : date
   - **TotalPrice** : devise
   - **RewardPointsAdded :** nombre entier
7. Dans le champ **Nom** du volet Paramètres de requête, renommez la requête en *Achats*. Cliquez sur **Suivant**.
8. Dans l’écran d’actualisation des données, sélectionnez **Enregistrer**.

## Tâche 5 : ingérer les données client à partir des avis sur le site web
1. Dans Customer Insights, développez **Données** dans le menu de navigation de gauche et sélectionnez **Source de données**.
2. Sélectionnez **+ Ajouter une source de données**. Choisissez **Microsoft Power Query** et nommez la source *Site web*, puis sélectionnez **Suivant**.
3. Sélectionnez le connecteur **Texte/CSV**.
4. Entrez https://aka.ms/CI-ILT/WebReviews pour le chemin d’accès ou l’URL du fichier. Sélectionnez **Suivant**, puis **Transformer les données**.
5. Comme précédemment, sélectionnez **Transformer**, puis **Utiliser la première ligne comme en-têtes**.
6. Mettez à jour le type de données de ces colonnes :
   - **ReviewRating** : nombre entier
   - **ReviewDate** : date
7. Dans le champ **Nom** du volet Paramètres de requête, renommez la requête en *Avis*. Cliquez sur **Suivant**.
8. Dans l’écran Paramètres d’actualisation, sélectionnez **Enregistrer**.
