pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Adsrshpoojary07/test'
            }
        }

        stage('Install Newman') {
            steps {
                sh 'npm install -g newman'
            }
        }

        stage('Run Postman Collection') {
            steps {
                sh '''
                newman run 8.API_Chaining.json -e postman_environment.json -r htmlextra
                '''
            }
        }

        stage('Publish Results') {
            steps {
                junit 'results.xml'
            }
        }
    }
}
