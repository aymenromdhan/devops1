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
     
stage("Quality code Test") {
            steps {
           
             sh 'mvn sonar:sonar -Dsonar.projectKey=sonartest -Dsonar.host.url=http://192.168.1.51:9000 -Dsonar.login=squ_38ad215ce1f019d734c3fa84a33bcc25c2715e50'         
                 
               

            }
        }

     
    }
}
