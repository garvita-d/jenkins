pipeline {
    agent {
        // SIMPLEST WORKING SOLUTION - Use direct label assignment
        label 'docker-agent-alpine'
    }

    stages {
        stage('Verify Environment') {
            steps {
                script {
                    echo "Running on node: ${env.NODE_NAME}"
                    sh '''
                        echo "OS information:"
                        cat /etc/*-release || true
                        echo "Python version:"
                        python --version || echo "Python not found"
                    '''
                }
            }
        }
        stage('Build') {
            steps {
                echo "Building your application..."
                // Add your actual build commands here
                // Example: sh 'mvn clean package' or sh 'npm install && npm run build'
            }
        }
    }

    post {
        always {
            echo "Pipeline completed on ${env.NODE_NAME}"
        }
    }
}
