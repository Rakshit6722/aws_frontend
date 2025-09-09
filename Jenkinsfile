pipeline{
    // Use 'agent any' to run on the Jenkins controller (or a static agent).
    agent {
        docker {
            image 'node:18.17.1'
            lable 'docker-cloud'
        }
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
                // Place the junit step here to ensure it has the correct context.
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