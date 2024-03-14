@Library('docker') _
pipeline {
    agent any
    stages {
      stage('Cloning Git') {
        steps {
          git "https://github.com/${Votre_ID_Github}/alpinehelloworld.git"
        }
      }
    }
}
