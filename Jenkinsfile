pipeline {
    agent any

    stages {
        stage('Checkout GIT') {
            steps {
                echo 'Pulling...'
                    git branch: 'main',
                    url : 'https://github.com/aymenromdhan/devops1'
                
            }
        }
        stage('MVN INSTALL') {
            steps {
                sh 'mvn install'
            }
        }
        stage('MVN CLEAN') {
            steps {
                  sh 'mvn clean package -DskipTests=true'
            }
        }
    }
}
