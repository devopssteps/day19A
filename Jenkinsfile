pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the project..."
                // Simulating build step
                sh 'echo Hello World'
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                // Simulating test step
                sh 'exit 1' // Change to 'exit 1' to test failure notification
            }
        }
    }

    post {
        success {
            slackSend(
                channel: 'C09AK2QM6M6', 
                message: "✅ SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' completed successfully!\n${env.BUILD_URL}",
                color: '#36a64f'
            )
        }
        failure {
            slackSend(
                channel: 'C09AK2QM6M6', 
                message: "❌ FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed!\n${env.BUILD_URL}",
                color: '#ff0000'
            )
        }
    }
}
