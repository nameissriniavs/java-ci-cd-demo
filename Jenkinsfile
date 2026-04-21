pipeline {
    agent any

    tools {
        jdk 'JDK11'        // Make sure this exists in Jenkins
        maven 'Maven3'     // Configure in Global Tool Config
    }

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
