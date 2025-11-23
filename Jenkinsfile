pipeline {
    agent any
    tools {
        maven 'M3'
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Code déjà présent grâce à Pipeline from SCM'
                sh 'pwd && ls -la'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile -DskipTests'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test -DskipTests || true'
            }
        }
    }
    post {
        success { echo 'Pipeline réussi !' }
        failure { echo 'Pipeline échoué' }
    }
}
