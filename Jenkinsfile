pipeline {
    agent any

    stages {
        stage('Checkout GIT') {
            steps {
                echo 'Pulling...'
                git branch: 'main', url: 'https://github.com/raedgs/devops'
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
     
         stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('sonarqube-10.2.1'){
                sh 'mvn sonar:sonar'
            }
        }
         }
       
     
    }
}
