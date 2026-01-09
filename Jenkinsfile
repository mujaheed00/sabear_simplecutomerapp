pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the public repo
                git branch: 'main', 
                    url: 'https://github.com/betawins/Trading-UI.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "Installing dependencies..."
                // Example for Node.js: uncomment if needed
                // sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo "Building the project..."
                // Example for Node.js: uncomment if needed
                // sh 'npm run build'
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo "Archiving build artifacts..."
                // Replace 'dist/**' with your build output directory
                archiveArtifacts artifacts: 'dist/**', allowEmptyArchive: true
            }
        }
    }

    post {
        success {
            echo "✅ Build succeeded!"
        }

        failure {
            echo "❌ Build failed!"
        }

        always {
            cleanWs() // Clean workspace after every build
        }
    }
}
