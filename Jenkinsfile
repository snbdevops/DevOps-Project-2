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
        stage('Stage 2 - Build Stage'){
            steps {
                sh 'mvn clean deploy'
                }
            }
        }
    }