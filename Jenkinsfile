pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo "starting compile deliverable maven build project"
                sh 'mvn clean package'
            }
            post {
                success {
                    echo "arschiving artifacts of tomcat project for creating toma image"
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('create-docker-image') {
            steps {
                sh 'docker build -t tomcat-docker:$BUILD_ID .'
            }
        }
    }
}