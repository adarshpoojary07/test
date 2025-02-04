pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', credentialsId: '839ac8c4-4f74-4334-81d1-4b20906f5221', url: 'https://github.com/Adsrshpoojary07/test'
            }
        }

        stage('Install Newman') {
            steps {
                sh 'npm install -g newman'
            }
        }

        stage('Run Postman Collection') {
            steps {
                sh 'newman run 8.API_Chaining.json -e postman_environment.json --reporters cli,junit --reporter-junit-export results.xml'
            }
        }

        stage('Publish Test Results') {
            steps {
                junit 'results.xml'
            }
        }
    }
}
