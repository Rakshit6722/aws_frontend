pipeline{
    agent {
        dockerContainer {image 'node:18.17.1'}
    }

    stages {
        stage('Install Dependencies'){
            steps{
                


                echo "Installing dependencies..."
                sh "npm install"
            }
        }



        stage('Run Tests'){
            steps{
                echo "Testing..."
                sh "npm run test:ci"
            }
        }

        stage ('Build'){
            steps{
                sh "npm run build"
            }
        }
    }

    post {
        always {
            junit 'reports/junit.xml'
        }
    }
}