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
                withSonarQubeEnv('sonar') {
                   sh "sonar-scanner"
                }
             }
          }

    }
}
