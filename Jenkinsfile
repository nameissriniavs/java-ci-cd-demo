pipeline {
    agent any

    tools {
        // REMOVE jdk/maven tool bindings (causing your first error)
    }

    stages {

        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/nameissriniavs/java-ci-cd-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn -version'
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
            }
        }
    }

    post {
        always {
            cleanWs()
            echo 'Pipeline completed'
        }
    }
}
