pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                git branch: 'feature', credentialsId: 'bf8146f1-825f-4e4c-9546-777e0e53fe21', url: 'https://github.com/brahmini-reddy/jenkins-repo.git'
            }
        }
        stage('mvn compile') {
            steps {
                powershell "mvn compile"
            }
        }
        stage('mvn test') {
            steps {
                powershell "mvn test"
            }
        }
        stage('mvn package') {
            steps {
                powershell "mvn package"
            }
        }
         stage('Deploy to tomcat') {
            steps {
                powershell "Copy-Item -Path C:/Users/sivar/.jenkins/workspace/declarative-pipeline-sample/target/june-java.war -Destination C:/Users/sivar/Downloads/apache-tomcat-9.0.89-windows-x64/apache-tomcat-9.0.89/webapps -Recurse -Force"
            }
        }
    }
}
