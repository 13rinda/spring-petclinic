pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh './mvnw clean' 
            }
        }
         stage('test') {
            steps {
                sh './mvnw test' 
            }
        }
        stage('package') {
            steps {
                sh './mvnw package' 
            }
        }
        stage('deploy') {
            steps {
                sh './mvnw deploy' 
            }
        }
    }
}



