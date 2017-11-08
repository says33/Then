pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                checkout scm
            }
        }
         stage('SonarQube analysis') {
             steps {
                script {
                      scannerHome = tool 'sonnarqube'
                      echo "${scannerHome}"
                }
                withSonarQubeEnv('sonarQubeServer') {
                   sh "${scannerHome}/bin/sonar-scanner"
                }
             }
          }

    }
}
