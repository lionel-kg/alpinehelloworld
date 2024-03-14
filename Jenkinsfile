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
    }
}
