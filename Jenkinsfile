pipeline {
    agent {
        // Option 1: Use dockerContainer (correct syntax for Docker agents)
        dockerContainer {
            image 'jenkins/agent:latest-py'  // Matches your configured template
            label 'docker-agent-alpine'     // The label you want to use
            args '-v /tmp:/tmp'             // Optional volume mounts
        }

        // Option 2: Use label directly (if you just want to use the labeled agent)
        // label 'docker-agent-alpine'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building on agent: ${env.NODE_NAME}"
                sh 'python --version'  // Verify Python
                // Add your build steps here
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
