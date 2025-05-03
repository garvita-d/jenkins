pipeline {
    agent {
        // Correct dockerContainer syntax for your Jenkins version
        dockerContainer {
            image 'jenkins/agent:latest-py'  // Must match your configured image
            // Only these options are allowed:
            // - image (required)
            // - connector (optional)
            // - credentialsId (optional)
            // - dockerHost (optional)
            // - remoteFs (optional)
        }
    }

    stages {
        stage('Build') {
            steps {
                echo "Building on agent: ${env.NODE_NAME}"
                sh 'python --version'  // Verify environment
                // Add your build commands here
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
