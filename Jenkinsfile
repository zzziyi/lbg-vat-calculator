pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'YOUR VAT CALCULATOR REPO HERE'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
            withSonarQubeEnv('sonar-qube-ziyi') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}