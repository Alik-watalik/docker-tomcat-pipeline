pipeline {
    agent any
    stages {
        stage('Build Application') {
            steps {
                sh 'mvn -f pom.xml clean package'
            }
            post {
                success {
                    echo "big wet anal ass of tori black"
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('Create Tomcat Docker Image'){
            steps {
                sh "docker build -t sampleapp:$BUILD_ID ."
            }
        }
    }
}