pipeline {
    agent any

    parameters {
        booleanParam(name: 'SKIP_TEST', defaultValue: false, description: 'Skip the test stage')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Test') {
            when {
                expression { return !params.SKIP_TEST }
            }
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            when {
                allOf {
                    branch 'main'
                    expression { currentBuild.currentResult == 'SUCCESS' }
                }
            }
            steps {
                echo 'Deploying the project...'
            }
        }
    }
}

