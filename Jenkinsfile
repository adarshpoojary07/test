pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Adsrshpoojary07'
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
                newman run API_Chaining_with_token.json -e postman_environment.json \
                --reporters cli,junit --reporter-junit-export results.xml
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
