pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout réussi via Pipeline from SCM !'
                sh 'pwd && ls -la'
            }
        }
        stage('Informations') {
            steps {
                echo 'Ce pipeline montre que Jenkinsfile est bien chargé depuis GitHub'
                echo "Branche : ${env.BRANCH_NAME}"
                echo "Build numéro : ${env.BUILD_NUMBER}"
                sh 'java -version'
                sh 'mvn -version'
            }
        }
        stage('Fin') {
            steps {
                echo 'Pipeline from SCM fonctionne parfaitement !'
            }
        }
    }
    post {
        success { echo 'ROND BLEU — Pipeline from SCM validé !' }
        failure { echo 'Échec du pipeline' }
    }
}
