pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                script {
                    git branch: 'main', 
                        url: 'https://github.com/sommygee/jenkins-git-integration.git'
                }
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo '✅ Build and Tests Successful!'
        }
        failure {
            echo '❌ Build Failed! Check logs for issues.'
        }
    }
}

