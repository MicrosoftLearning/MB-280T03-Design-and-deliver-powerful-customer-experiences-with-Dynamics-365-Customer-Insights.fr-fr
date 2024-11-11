---
lab:
  title: "Labo\_4.1\_: créer un parcours basé sur un déclencheur"
---

# Parcours d’apprentissage 4 : créer des parcours

## Labo pratique 4.1 : créer un parcours basé sur un déclencheur 

### Présentation du labo

#### Scénario
Maintenant que nous avons créé nos 3 e-mails, il est temps de créer un parcours pour envoyer les e-mails à nos clients. Nous enverrons notre premier e-mail à nos clients pour les informer de la prochaine machine à café intelligente Airpot.

Les clients qui interagissent avec cet e-mail seront ensuite divisés en deux sections : les clients qui possèdent déjà un ancien modèle Airpot et les clients qui n’en ont pas. Pour nos propriétaires d’Airpot existants, nous enverrons un e-mail les encourageant à acheter un nouveau modèle. S’ils interagissent avec un lien de cet e-mail, un vendeur qui les contactera directement.

Les propriétaires existants qui n’ont pas cliqué sur un lien recevront un autre e-mail publicitaire du produit. Cet e-mail sera également envoyé aux propriétaires qui ne possèdent pas d’Airpot.


### Ce dont vous avez besoin :
- Un ordinateur avec un environnement Dynamics 365 Customer Insights - Journeys.

## Exercice 1 : créer un parcours en temps réel

### Tâche 1 : créer un parcours
1.  Connectez-vous à Dynamics 365 Customer Insights - Journeys.
2.  Accédez à la zone de travail **Parcours en temps réel**.
3.  Dans **Engagement**, sélectionnez **Parcours**.
4.  Dans la barre de commandes, cliquez sur **+ Nouveau parcours**. Si vous êtes invité à utiliser Copilot pour créer votre parcours, sélectionnez **Ignorer et créer à partir de zéro**.
5.  Dans **Nommer le parcours**, entrez *Campagne de lancement de la machine intelligente Airpot*.
6.  Dans **Choisir le type de parcours**, sélectionnez **Basé sur un déclencheur**.
7.  Dans **Choisir un déclencheur**, recherchez et sélectionnez **Lien d’e-mail cliqué**.
8.  Dans **Choisir un e-mail**, recherchez et sélectionnez votre **e-mail de campagne de machine intelligente**.
9.  Cliquez sur **Créer**.

### Tâche 2 : configurer l’entrée de parcours
1. Accédez à la section **Paramètres de parcours**, qui sera développée sur le côté droit de l’écran. La section **Entrée** doit être ouverte.
2. Laissez **Exclure par segments** vide.
3. Dans la section **Répéter**, sélectionnez Immédiatement.
4. Dans la section **Fuseau horaire**, choisissez votre fuseau horaire.
5. Dans **Démarrer**, sélectionnez Aujourd’hui. Définissez l’heure sur 15 minutes à partir de maintenant. (Vous pouvez renseigner directement ce champ.)
6. Dans **Fin**, sélectionnez Demain.

### Tâche 3 : configurer l’objectif du parcours
1.  Accédez aux paramètres du parcours à droite, qui ressemblent à une liste d’icônes. Pointez sur chaque icône pour afficher le nom de chaque onglet. Sélectionnez la section **Objectif**.
2.  Dans *Objectif de ce parcours*, sélectionnez **Envoyer une notification générale**.
3.  Dans *L’objectif est atteint lorsque*, sélectionnez **Une personne a cliqué sur au moins un lien**.
4.  Dans *Nombre de personnes nécessaires*, entrez *50*. Laissez le pourcentage sélectionné.

### Tâche 4 : ajouter une branche d’attribut
1. Dans le concepteur de parcours, cliquez sur l’**icône plus (+)** dans la vignette **Lien d’e-mail cliqué**.
2. Dans la section *Conditions*, sélectionnez **Branche d’attribut**.
3. Dans **Nom d’affichage** à droite, entrez *Possède déjà une machine Airpot*.
4. Sélectionnez **Branche 1**. Dans Nom d’affichage, entrez *Possède une machine Airpot*.
5. Sélectionnez **+ Ajouter des conditions**.
6. Dans **Choisir un attribut**, recherchez **Description (description)** sous Contact.
7. Remplacez la valeur Égal à par Contient.
8. Dans **Valeur**, entrez *Airpot*.
9. Revenez au concepteur de parcours. Cliquez sur l’**icône plus (+)** sous Branche 1.
  - Sélectionnez **E-mail**.
  - Dans **Sélectionner un e-mail**, choisissez **E-mail Mettre à niveau vers Airpot**.
10.  Cliquez sur l’**icône plus (+)** sous la vignette Envoyer un e-mail.
  - Sélectionnez **Attendre le déclencheur**.
  - Dans **Choisir un type de condition de branche**, sélectionnez **Le message précédent obtient une interaction**.
  - Dans **Choisir une interaction**, sélectionnez **Lien d’e-mail cliqué**.
  - Dans **Quelle est la limite de temps ?**, entrez 10 minutes.
11. Dans le chemin **Oui**, cliquez sur l’**icône plus (+)**.
  - Sélectionnez **Tâche** dans la section Activités.
  - Dans Choisir un modèle, sélectionnez **Effectuer le suivi avec le client**.
  - Les champs Objet et Attribuer à sont renseignés automatiquement.
  - Définissez **Due après** sur *2 semaines*.
12. Dans le chemin **Non** correspondant (sous la branche if/then Lien d’e-mail cliqué), cliquez sur l’**icône plus (+)**.
  - Sélectionnez **Envoyer un message électronique**.
  - Dans **Sélectionner un e-mail**, choisissez **Rappel de campagne Smart Machine**.
13. Revenez au concepteur de parcours. Recherchez la vignette **Attribut**. Nous allons maintenant configurer la branche **Non**. Pour les clients qui ne possèdent pas encore d’Airpot, nous enverrons le troisième e-mail.
  - Sélectionnez le signe **+** sous **Autre**.
  - Sélectionnez **E-mail**.
  - Sous Sélectionner un e-mail, sélectionnez **Rappel de campagne Smart Machine**.
14. **Enregistrez** le parcours.
15. Passez en revue le parcours. Apportez les modifications finales.
16. Cliquez sur **Publier**. Attendez que le parcours soit publié.
