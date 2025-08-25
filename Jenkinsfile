pipeline{
    agent {
        docker{
            image 'cypress/browsers:latest'
        }
    }
    stages{
        stage("install dependencies"){
            steps{
                sh 'npm ci'
            }
        }

        stage("run tests"){
            steps{
                sh 'npx cypress run'
            }
        }
    }
}
