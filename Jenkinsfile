pipeline {
    agent any

    tools {
        maven 'mymaven'
        jdk 'jdk17'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/<your-username>/java-ci-cd-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.war'
            }
        }
    }
}
