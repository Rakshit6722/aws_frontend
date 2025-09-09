pipeline {
    agent {
        docker {
            image 'node:18'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Install Dependencies'){
            steps{
                sh "npm install"
            }
        }
        stage('Run Tests'){
            
            steps{
                sh "npm run test:ci"

                junit 'reports/junit.xml'

            }
        }
        stage ('Build'){
            steps{
                sh "npm run build"
            }
        }
    }
}