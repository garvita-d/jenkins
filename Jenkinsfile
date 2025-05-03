pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    extensions: [],
                    userRemoteConfigs: [[
                        url: 'https://github.com/garvita-d/jenkins',
                        credentialsId: 'your-credentials-id'  // Only if private repo
                    ]]
                ])
            }
        }
        stage('Build') {
            steps {
                echo "Building on ${env.NODE_NAME}"
                // Your build steps
            }
        }
    }
}
