pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/nameissriniavs/java-ci-cd-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
            }
        }
    }
}
