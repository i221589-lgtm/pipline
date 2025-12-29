pipeline {
    agent any
    parameters{
        booleanParam(
            name: 'executeTests',
            defaultValue: true,
            description: 'Run test stage or skip it'
        )
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Commands for build go here
            }
        }

        stage('Test') {
            when{
                expression{
                    return params.executeTests == true
                }
            }
            steps {
                echo 'Testing...'
                // Commands for testing go here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Commands for deployment go here
            }
        }
    }
    post{
        always {
            echo 'Pipeline finished (always runs)'
        }
        failure {
            echo 'Pipeline failed!'
        }

    }
}
