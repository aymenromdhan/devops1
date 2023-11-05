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
        stage('Build') {
            steps {
                // Étape de nettoyage du projet
                sh 'mvn clean'
                // Étape de compilation du projet
                sh 'mvn compile'
            }
        }
    }
}
