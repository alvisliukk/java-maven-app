pipeline {
   agent any
    
    stages {
        stage('Build install') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            
        }
        stage('Deliver') {
            steps {
                echo 'deliver'
            }
        }
    }
}
