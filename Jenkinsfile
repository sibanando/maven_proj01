pipeline {
    agent any
    tools {
         maven 'MAVEN_HOME'
       }

    stages {
        stage('Hello') {
            steps {
               git 'https://github.com/sibanando/maven_proj01'
               echo "sucessful"
            }
        }
        stage('maven') {
           steps {
                sh 'mvn clean  -f pom.xml'
              }
        }
    }
}

