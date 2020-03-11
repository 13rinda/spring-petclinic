pipeline {
    agent any
   

    stages {
        stage('build') {
            steps {
                sh 'mvn clean' 
            }
        }
         stage('test') {
            steps {
                sh 'mvn test' 
            }
        }
        stage('package') {
            steps {
                sh 'mvn package' 
            }
        }
        
	stage('expression-branch') {
    agent label:'some-node'
    when {
    expression {
        return env.BRANCH_NAME != 'master';
        }
    }
    steps {
        echo 'run this stage - when branch is not equal to master'
        stage('deploy') {
            steps {
                sh 'mvn deploy' 
            }
        }
    }
}

        
    }
}



