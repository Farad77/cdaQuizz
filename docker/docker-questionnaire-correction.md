# Correction du Questionnaire sur Docker

## Questions à choix unique (en français)

1. Quelle commande Docker est utilisée pour construire une image à partir d'un Dockerfile ?
   
   Réponse correcte : b) docker build
   
   Explication : La commande `docker build` est utilisée pour construire une image à partir d'un Dockerfile. Elle lit les instructions du Dockerfile et crée une image en conséquence.

2. Quel est le rôle principal de Docker Hub ?
   
   Réponse correcte : c) Stocker et partager des images Docker
   
   Explication : Docker Hub est un service de registre cloud qui permet de stocker, partager et gérer des images Docker. C'est un référentiel centralisé pour la découverte, la distribution et la gestion des changements des images de conteneurs.

## Questions ouvertes (en anglais)

1. Briefly explain the difference between a Docker image and a Docker container.

   Réponse modèle : 
   A Docker image is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, system tools, libraries, and settings. It's essentially a template.
   
   A Docker container, on the other hand, is a running instance of an image. It's the actual execution of the application, created from an image. Containers can be started, stopped, moved, and deleted, and each one is an isolated and secure application platform.

2. What are two key benefits of using Docker in software development and how does it achieve them?

   Réponse modèle :
   Two key benefits of using Docker in software development are:

   1. Consistency across environments: Docker ensures that the application runs the same way in development, testing, and production environments. This is achieved by packaging the application and its dependencies into a container, which can be run consistently on any system that supports Docker.

   2. Improved efficiency and productivity: Docker allows developers to quickly set up and tear down development environments, and to easily share their work with others. This is achieved through the use of Dockerfiles and Docker images, which can be version-controlled and shared via Docker Hub or other registries.

   Docker achieves these benefits by using containerization technology, which allows applications to be packaged with all their dependencies and run in isolated environments, regardless of the host system's configuration.

