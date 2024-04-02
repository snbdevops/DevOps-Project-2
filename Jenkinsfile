pipeline {
    agent {
        node {
            label 'maven'
        }
    }
    environment{
        PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
    }

    stages {
        stage('Stage 2 - Build Stage') {
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage('Stage 3 - SonarQube Stage') {
            environment {
                scannerHome = tool 'sonarqube-scanner'
            }
            steps {
                withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
                sh "${scannerHome}/bin/sonar-scanner"
            }
        }
    }
}
}