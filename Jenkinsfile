pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Adsrshpoojary07/test'
            }
        }
        stage('Run Postman Tests') {
            steps {
                sh 'newman run 8.API_Chaining.json -e postman_environment.json -r htmlextra'
            }
        }
    }
}
