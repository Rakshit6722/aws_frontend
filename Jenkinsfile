pipeline {
    agent {
        docker {
            image 'node:18.17.1'
            label 'docker-cloud'
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