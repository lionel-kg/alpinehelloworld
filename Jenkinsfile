pipeline {
    agent any
    stages {
      stage('Cloning Git') {
        steps {
          git "https://github.com/${Votre_ID_Github}/alpinehelloworld.git"
        }
      }
         stage('Build Image') {
          steps {
              script {
                    // Construction de l'image Docker
                   docker.build("${IMAGE_NAME}:${IMAGE_TAG}", '.')
              }
          }
      }
        stage('Push Image') {
                steps {
                    script {
                        // Connexion à Docker Hub
                        docker.withRegistry('https://index.docker.io/v2/', "${DOCKERHUB_ID}") {
                            // Pousser l'image vers Docker Hub
                            docker.image("${IMAGE_NAME}:${IMAGE_TAG}").push()
                        }
                    }
                }
            }
    }
}
