pipeline {
    agent any
     tools {
         maven 'MAVEN_HOME'
       }

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sibanando/maven_proj01'
            }
        }
        stage('Maven') {
            steps {
                sh 'mvn clean install -f pom.xml'
            }
        }
        stage('Deploy on docker') {
            steps {
                
               sh 'docker rmi -f tomcatweb'
               sh 'docker build -t tomcatweb .'

               sh 'docker run -d -p 9000:8080  tomcatweb'
            }
        }
    }
}

