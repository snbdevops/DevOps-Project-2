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
        stage('Stage 2 - BUILD') {
            steps {
                sh 'mvn clean deploy'
            }
        }
    }
}