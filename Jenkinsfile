// This is a Declarative Pipeline script
pipeline {
    agent any

    stages {
        // Stage 1: Build
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'echo "Application built successfully!"'
            }
        }

        // Stage 2: Test
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "Tests passed!"'
            }
        }
    }

    // Post-build actions for the entire pipeline
    post {
        always {
            echo 'I will always run, even if the build fails.'
        }
        success {
            echo 'Build was successful! Archiving results.'
            // Example: archive artifacts
            // archiveArtifacts artifacts: 'build/**/*.zip'
        }
        failure {
            echo 'Build failed! Sending a notification.'
            // Example: send an email
            // mail to: 'dev@example.com', subject: "Pipeline Failed: ${currentBuild.fullDisplayName}"
        }
    }
}