pipeline {
    agent {
        // Option 1: Use your existing Docker agent with Python (if Alpine isn't strictly needed)
        docker {
            image 'jenkins/agent:latest-py'  // Matches your configured template
            label 'docker-agent-alpine'  // Keep the label if you must, but ensure the image is correct
        }

        // Option 2: Use a generic label (if you have other agents available)
        // label 'docker'  // Use this if you have a general-purpose Docker agent
    }

    stages {
        stage('Build') {
            steps {
                echo "Building on agent: ${env.NODE_NAME}"
                sh 'python --version'  // Verify Python (since the image is Python-based)
                // Add your build steps here (e.g., `mvn package` or `npm install`)
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                // Add test commands here
            }
        }
    }

    post {
        always {
            echo "Pipeline completed on agent: ${env.NODE_NAME}"
        }
    }
}
