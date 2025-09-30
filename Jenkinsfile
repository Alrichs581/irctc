pipeline {
    agent any
    environment {
        PATH = '/opt/maven/biin:$PATH'
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage('SonarQube analysis') {
            environment {
                scannerHome = tool 'alain-sonar-scanner'
            }
            steps {
                withSonarQubeEnv('Targ-sonarqube-server') {
                    sh "${scannerHome}/bin/sonar-scanner"
        }
    }
}
