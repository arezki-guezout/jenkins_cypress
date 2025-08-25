pipeline{
    agent {
        docker{
            image 'cypress/browsers:latest'
            args '--entrypoint='
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
    post{
        always {
            archiveArtifacts artifacts: 'cypress/reports/html/*.html', followSymlinks: false
        }
    }
}
