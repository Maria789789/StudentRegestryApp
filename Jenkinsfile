pipeline {
    agent any


    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Maria789789/StudentRegestryApp'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    bat 'npm install' 
                }
            }
        }

        stage('Start Application and Run Tests') {
            steps {
                script {
                    bat 'start /b npm start'
                }
            }
        }

        stage('Run tests') {
            steps {
                script {
                    bat 'npm test'
                }
            }
        }
    }

    post {
        always {
            echo 'CI pipeline completed'
        }
    }
}