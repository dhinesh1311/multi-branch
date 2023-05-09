pipeline {
    agent any
    tools {
        maven 'maven3' 
    }
    stages {
        stage ('Build') {
            steps {
                sh 'mvn clean package'
                sh 'mv target/onlinebookstore*.war target/newbook.war'
            }
        }
        stage('Docker Build') {
            steps {
                script {
                    sh 'docker build -t comdevops/multi:v1 .'
                    sh 'docker images'
                }
            }
        }
    }
}
