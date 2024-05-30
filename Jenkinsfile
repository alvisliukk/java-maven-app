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
        
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
        
        stage('Generate Versioning File') {
            steps {
                script {
                    def currentTime = new Date().format("yyyy-MM-dd HH:mm:ss")
                    bat "echo ${currentTime} > version.txt"
                }
            }
        }

        stage('Commit and Push') {
            steps {
                script {
                    bat 'git add version.txt'
                    bat 'git config --global user.email "alvis@example.com"'
  				    bat 'git config --global user.name "Alvis Liu"'
                    
                    bat 'git commit -m "Update version.txt with current timestamp"'
                    bat 'git push'
                }
            }
        }
        
    }
}
