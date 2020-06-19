# Docker_SalaryPred
With Docker - Create API of ML model using flask

## Etapes pour déployer un model ML

1. Installer Flask et Docker
2. Sérialiser votre modèle Scikit-Learn (Vous pouvez utiliser Pickle, ou Joblib)
3. Créer un service api.py qui vous permettra d'exposer votre modèle via un webservice Flask
  * Vérifier que votre code api.py fonctionne correctement
  * Accédez à l'adresse pour vérifier que votre code fonctionne
4. Cette étape peut varier en fonction des projets, il s'agit de construire le Dockerfile en suivant différentes étapes: 
  * Partez d'une image de base FROM ubuntu, python, git...
  * Clonez le répertoire Git pour mettre le code dans votre WORKDIR /app
  * Installez les dépendances avec requirements.txt
  * EXPOSE le port de votre application
  * Définir le CMD pour démarrer votre serveur Flask
5. Buildez l'image Docker
6. Démarrez le conteneur
7. Vérifiez avec Insomnia que votre API fonctionne toujours correctement et que les prédictions de votre modèle sont les . bonnes.
8. Vous pouvez push sur un registre d'image Docker comme le Dockerhub votre image et délivrer votre application en prod.

## Solution pour afficher la prédiction
1. Créer un dossier contenant tous les dossiers/fichiers de app.zip 
2. Faire pip install -r requirements.txt pour installer les bonnes versions des librairies
3. Faire export FLASK_APP=server.py et flask run pour lancer le serverlocal
4. Ouvrir Insomnia et faire une request POST avec http://127.0.0.1:5000/api
5. Cliquer sur le format JSON, écrire par exemple: {"exp":10}
Normalement ça sort une prédiction 

## Solution pour créer l'image Docker et Docker-compose
1. Bien mettre toutes les librairies avec la bonne version dans le requirement.txt (Flask)
2. Faire un docker-compose down et docker-compose up après avoir fait un docker-compose.yml
3. Tester sur Insomnia en faisant une request POST comme précedemment
NB: faire un docker-compose up permet de build l'image docker, en cas de modification, 
il est possible de faire un docker-compose build pour re-build l'image 
