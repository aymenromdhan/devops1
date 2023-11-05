pipeline {
    agent any

    stages {
        stage('Checkout GIT') {
            steps {
                echo 'Pulling...'
                git branch: 'main', url: 'https://github.com/aymenromdhan/devops1.git'
            }
        }
        stage('MVN CLEAN') {
            steps {
                // Nettoie le projet en utilisant Maven
                sh 'mvn clean'
            }
        }
        stage('MVN COMPILE') {
            steps {
                // Compile le projet en utilisant Maven
                sh 'mvn compile'
            }
        }
        stage('Deploy to Nexus') {
            steps {
                sh 'mvn deploy -DskipTests'  // Déployer sur Nexus en sautant les tests
            }
          
        }
     
         stage ('Scan and Build Jar File') {
            steps {
               withSonarQubeEnv(installationName: 'Sonar', credentialsId: 'sonartest') {
                sh 'mvn clean package sonar:sonar'
                }
            }
        }
       
     
    }
}
