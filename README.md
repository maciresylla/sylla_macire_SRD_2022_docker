# sylla_macire_SRD_2022_docker

# DockerFile(s) pour builder notre image :
##    Dockerfile :
            FROM node:16

            WORKDIR /app

            COPY package.json ./

            RUN npm install --force

            COPY . .

            CMD [ "npm", "start" ]
            
## Contruire une image            
    docker build -t maciresylla/NomFutureImage .
## Lancer une image
    docker run idDeCompte/NomImage

# Démarrer les container avec Docker-Compose

## Créer un fichier docker-compose.yml à  la racine
    version: "3"
    services:
      my_front:
        image: idDeCompte/NomImageFront
        container_name: new_front
      my_back:
        image: idDeCompte/NomImageBack
        container_name: new_back
        
## Se placer à la racine et lancer docker-compose
  
  docker-compose up
  
### Voir toutes les container

 docker ps -a
 
 # Architecture de l'application 
 
  ![image](https://user-images.githubusercontent.com/105586456/168476909-aa5dd594-93b2-447e-9039-f31edc7cb8b3.png)
