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
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8080' 
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