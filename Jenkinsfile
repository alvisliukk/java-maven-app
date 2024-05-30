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
                bat 'git pull origin master'
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
                
                	def localBranch = "C:\Users\kk_tu\git\java-maven-app\";
                    
                    bat 'move version.txt ${localBranch}'
                    bat 'git add ${localBranch}\version.txt'
                    
                    bat 'cd ${localBranch}'
                    bat 'git commit -m "Update version.txt with current timestamp"'
                    bat 'git push origin master'
                }
            }
        }
        
    }
}
