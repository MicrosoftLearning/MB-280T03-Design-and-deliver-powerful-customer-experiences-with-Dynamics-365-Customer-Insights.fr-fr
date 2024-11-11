---
lab:
  title: "Labo\_2.2\_: créer un profil client unifié"
---

# Labo 2.2 : créer un profil client unifié

## Parcours d’apprentissage 2 : utiliser des profils client unifiés dans Dynamics 365 Customer Insights - Data

Après l’ingestion des données brutes provenant de vos sources de données dans les entités, vous allez maintenant commencer le processus de mappage, de mise en correspondance et de fusion pour créer un profil client unifié unique en fusionnant les données de chaque source de profil client. Pour ce faire, vous devez d’abord mapper les entités ingérées avec un modèle standard et sélectionner la clé primaire pour chaque entité profilée. À la fin de cette opération, vous allez ensuite créer votre règle de correspondance qui sera utilisée pour faire correspondre les contacts de toutes les entités client. Enfin, l’exécution de la fusion permettra de créer un ensemble commun de clients uniques dont les profils issus de toutes les entités client correspondent en utilisant vos règles de correspondance. Votre objectif vise à découvrir le nombre de profils client uniques que Contoso Retail possède au niveau des diverses sources de données.

## Exercice 1 : unifier les données

### Tâche 1 : mapper les contacts avec les types de données courants
1. Connectez-vous à Customer Insights - Data à l’adresse https://home.ci.ai.dynamics.com.
2. Dans le menu de navigation de gauche, développez **Données** et sélectionnez **Unifier**.
3. Dans la section Données client, sélectionnez **Démarrage**.
4. Dans l’écran **Décrire les données client à unifier**, sélectionnez **+ Démarrage**.
5. Sélectionnez les tables qui représenteront le profil client. Ces tables sont les suivantes :
   - Contacts (E-commerce)
   - Clients (Fidélité)
6. Sélectionnez **Appliquer**.
7. Les mappages de votre table source avec les types de modèle standard vous sont maintenant présentés. Vous pouvez examiner les types dans le tableau.
8. Vous devez choisir une « Clé primaire » pour chaque entité ingérée. La clé primaire doit être une référence unique. Pour les contacts d’e-commence, sélectionnez **ContactId** comme clé primaire.
9. Les données de contacts d’e-commerce contiennent une colonne nommée **Abonné aux e-mails** qui sera mappée avec un type incorrect, Identity.Service.Email, en raison du nom. Ouvrez la liste déroulante de cette colonne et sélectionnez l’option vide (rien/vierge). Si nous ne le faisons pas, le comportement par défaut du système consiste à fusionner ce champ avec le champ E-mail, ce que nous ne voulons pas.
10. Sélectionnez **Fidélité des clients** sous Tables et définissez **LoyaltyID** comme clé primaire.
11. Sélectionnez **Enregistrer les colonnes sources** dans le coin supérieur gauche.
12. Sélectionnez le bouton **Suivant**, puis à nouveau **Suivant** pour ignorer la vérification des doublons et passer à l’étape des règles de correspondance.

### Tâche 2 : spécifier l’ordre de correspondance
Pour la phase suivante, vous devez sélectionner l’ordre dans lequel fusionner les profils. Vous pourrez fusionner des attributs pour vous assurer que les profils unifiés sont complets, ainsi que la priorité des sources à utiliser pour ces attributs.
1. Vous devez sélectionner la source de profil la plus complète ou précise comme source principale (première). Vérifiez que **Contacts : e-commerce** est la source principale (première) (ou déplacez-la si ce n’est pas déjà fait).
2. Cochez la case pour **Inclure tous les enregistrements**.
3. Vérifiez que **Clients : fidélité** est la deuxième source dans la liste. Choisissez d’**Inclure tous les enregistrements**.

### Tâche 3 : créer une règle de correspondance
Dans cette tâche, vous allez créer une règle simple utilisée pour mettre en correspondre tous les enregistrements. Les règles peuvent comporter une seule (par exemple, basée sur l’ID) ou plusieurs (par exemple, FullName, PostCode, date de naissance) conditions. Pour plus d’informations sur les règles de correspondance, consultez la documentation Customer Insights.
1. Il existe un indicateur d’avertissement sur la **ligne Clients : fidélité**. Sélectionnez **+ Ajouter une règle** ou l’icône **+** à droite.
2. Ajoutez la première condition en utilisant FullName :
   - Pour la table Contacts : e-commerce, sélectionnez le champ **FullName**.
   - Pour la table Clients : fidélité, sélectionnez le **FullName**.
   - Laissez la liste déroulante Normaliser vide.
   - Définissez le niveau de précision sur **De base** à l’aide du champ déroulant.
   - Définissez la valeur de précision sur **Haute** à l’aide du curseur.
3. Entrez le nom **Nom complet, e-mail** pour la règle.
4. Ajoutez une deuxième condition pour l’adresse e-mail en sélectionnant **+ Ajouter**, puis sélectionnez **Ajouter une condition**.
   - Pour la table Contacts : eCommerce, sélectionnez le champ **E-mail**.
   - Pour la table Clients : fidélité, sélectionnez le champ **EMail**.
   - Laissez la liste déroulante Normaliser vide.
   - Définissez le niveau de précision sur **De base**.
   - Définissez la valeur de précision sur **Haute**.
5. Cliquez sur **Terminé**.
6. Sélectionnez **Suivant**, **Suivant** et **Créer des profils clients**.

Customer Insights met désormais en correspondance les données client de toutes vos sources d’information client pour identifier le nombre de profils client uniques que vous auriez en fonction de vos règles. Discutez avec la classe : combien de clients uniques avez-vous lors de la combinaison de vos jeux de données ?

### Tâche 4 : précision
Dans la tâche 3, nous avons utilisé haute précision dans la règle de correspondance avec le nom complet. Dans cette tâche, vous allez ajuster le niveau de précision pour créer un nombre plus élevé de correspondances en incluant les correspondances d’une confiance inférieure (ce qui entraîne un nombre inférieur de profils uniques).

**Remarques sur la précision :**
- Le niveau Exact sur le côté droit de l’échelle correspond aux enregistrements où votre condition a une correspondance exacte. Sélectionnez l’un des autres niveaux pour une corresponce aux enregistrements qui ne sont pas identiques à 100 %.
- Le niveau Élevé correspond à des cas où la précision est plus importante que la portée, telle qu’un service financier à un client spécifique.
- Le niveau Faible correspond aux cas où l’inverse est vrai, comme une campagne marketing.
- Le niveau Moyen sert d’option intermédiaire.

1. Dans Customer Insights, dans le menu de navigation de gauche, développez **Données**. Sélectionnez **Unifier.**
2. Sous Règles de correspondance, sélectionnez **Modifier**.
3. Développez la règle **Clients : fidélité** et sélectionnez le bouton **Modifier** pour ouvrir le volet des conditions **Nom complet, e-mail**.
4. Dans Condition 1, sélectionnez **Aperçu** et notez les valeurs. Déplacez le curseur Précision pour la condition 1 de **Élevé** à **Faible**. Cliquez sur **Terminé**.
5. Sélectionnez **Suivant**, **Suivant**, puis **Créer des profils client**.
6. Attendez que le processus de correspondance se termine.
7. Une fois le processus de correspondance terminé, cliquez sur **Modifier** sur les règles de correspondance. Sélectionnez le **menu des points verticaux** en regard de la règle **Nom complet, e-mail**, puis sélectionnez **Aperçu** pour afficher les résultats de correspondance et le score. Cela montre comment Customer Insights a mis en correspondance les tables de données en fonction des règles que vous avez définies. Certains profils ont été créés avec un niveau de confiance plus faible pour la correspondance.
8. Fermez l’aperçu et sélectionnez Modifier. Sélectionnez le bouton Aperçu sous Condition 1. Ici, vous pouvez afficher un aperçu du nombre d’enregistrements avec et sans correspondance pour la condition Nom complet.
9. Dans Sans correspondance ou Avec correspondance, sélectionnez **Aperçu des données** pour afficher un aperçu des correspondances. Notez que les scores élevés ont une orthographe exacte, mais peuvent correspondre même si le format de nom (prénom, nom/nom, prénom) est différent. Avec les scores faibles, notez comment les correspondances sont effectuées même lorsque les noms ne sont pas orthographiés de manière identique.
10. Fermez le volet Aperçu des critères et sélectionnez **Annuler**.

Discutez avec la classe : combien de profils client uniques avez-vous maintenant ?

### Tâche 5 : unifier les champs client
Il s’agit de la dernière phase du processus d’unification des données. Elle a pour but de rapprocher les données contradictoires et de définir les attributs qui seront utilisés dans votre profil client unifié. Un attribut fusionné est un attribut qui existe dans plusieurs sources de données et représente la même donnée. Par exemple, vous pouvez avoir « Adresse e-mail » à la fois dans les sources de données des clients e-commerce et des clients du programme de fidélité. Customer Insights tentera d’identifier les attributs à fusionner avec les types de données standard que nous avons définis à l’étape des champs sources.

1. Dans Customer Insights, dans le menu de navigation de gauche, développez **Données**. Sélectionnez **Unifier.**
2. Sous Vue de données unifiées, sélectionnez **Modifier**.
3. Dans les colonnes Client, observez comment les attributs issus de différentes sources de données qui sont de même type (par exemple, FirstName) ont été fusionnés.
4. Développez l’attribut fusionné **FirstName**. Vous devez voir que l’attribut FirstName dans E-commerce : contacts est classé numéro 1. Cela indique que, dans les cas où un profil client correspondant existe à la fois dans LoyaltyScheme et dans E-commerce, le FirstName tiré de E-commerce : contacts est le principal.
9. Sélectionnez **Suivant** puis **Créer des profils client**.
10. Attendez que le processus se termine.

Félicitations ! Vous avez réussi à ingérer, mapper, faire correspondre et unifier des données à partir de plusieurs sources dans Customer Insights afin de créer un profil client unifié qui permet d’obtenir des informations sur toute votre clientèle.

## Exercice 2 : rechercher des clients
Dans cet exercice, nous allons configurer des critères de recherche et de filtre pour permettre aux utilisateurs de Customer Insights de rechercher des profils client unifiés afin de pouvoir extraire rapidement des informations sur un client ou un groupe de clients spécifique.

### Tâche 1 : configurer l’index Rechercher des colonnes et filtrer
1. Dans Customer Insights, sélectionnez **Clients** dans le menu de navigation de gauche.
2. Sélectionnez **Index Rechercher et Filtrer**.
3. Certains champs spécifiques à la recherche client sont déjà ajoutés par défaut et vous pouvez en ajouter d’autres en sélectionnant **+ Ajouter** dans la barre d’outils.
4. Vérifiez que **CustomerId, FirstName, LastName, FullName, DateOfBirth, EMail, PostCode, Headshot, ContactId (eCommerce_Contacts)** et **LoyaltyId** sont sélectionnés. Désélectionnez tous les autres champs cochés. Sélectionnez **Appliquer**.
5. Cliquez sur **Enregistrer**.

### Tâche 2 : rechercher un enregistrement client
1. Dans Customer Insights, sélectionnez **Clients** dans le menu de navigation de gauche. Un ensemble de cartes client représentant les profils unifiés doit vous être présenté. Vous pouvez développer des cartes pour en savoir plus sur le client ou trier les cartes par différents champs. Essayez ces fonctionnalités en sélectionnant **Développer des cartes** et **Trier par** dans la barre d’outils.
2. Vous pouvez utiliser Rechercher des clients pour rechercher des attributs de texte relatifs aux profils client unifiés. (Par exemple, La recherche de « 24502 » effectue une recherche sur tous les attributs de texte et renvoie des correspondances et des correspondances partielles.)

Utilisez la barre de recherche pour répondre aux questions suivantes :
- Quelle est la date de naissance de Brian Gobble ? (Rechercher Brian Gobble)
- Quel client a l’ID de carte de fidélité LOYID_5707 ? (Rechercher LOYID_5707)
- Quel client a le code postal 24502 ? (Rechercher 24502)
