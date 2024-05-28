pipeline {
   agent any
    
    stages {
        stage('Build installing 1') {
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
