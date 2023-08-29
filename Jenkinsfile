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
                
               
               sh 'docker build -t tomcatweb1 .'

               sh 'docker run -d -p 9001:8080  tomcatweb1'
            }
        }
    }
}

