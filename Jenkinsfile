pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Adsrshpoojary07/test'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install -g newman'
            }
        }

        stage('Run Postman Collection') {
            steps {
                sh 'newman run 8.API_Chaining.json -e postman_environment.json'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
        success {
            echo 'Postman collection tests passed!'
        }
        failure {
            echo 'Postman collection tests failed!'
        }
    }
}
