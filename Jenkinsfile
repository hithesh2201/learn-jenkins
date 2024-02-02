pipeline {
//    agent {
//         label 'agent-1'
//     }
    agent any
    
    parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'qa', 'prod'], description: 'Select the deployment environment')
        string(name: 'VERSION', defaultValue: '1.0', description: 'Specify the application version')
    }

    options {
        timeout(time: 1, unit: 'HOURS') // Set a timeout for the entire pipeline
        ansiColor("xterm") 

    }

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building the application..."
                    // Add your build steps here
                    echo "Test"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "Running tests..."
                    // Add your test steps here
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying to ${params.ENVIRONMENT} environment, version ${params.VERSION}..."
                    // Add your deployment steps here
                }
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully. Sending notification..."
            // Add notification steps for successful builds
        }

        failure {
            echo "Pipeline failed. Sending notification..."
            // Add notification steps for failed builds
        }

        always {
            echo "Cleaning up..."
            // Add any cleanup steps that should run regardless of success or failure
            deleteDir()
        }
    }
}
