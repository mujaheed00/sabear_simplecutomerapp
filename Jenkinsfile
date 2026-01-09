pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout only the repo containing Jenkinsfile
                git branch: 'master', 
                    url: 'https://github.com/mujaheed00/sabear_simplecutomerapp.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "Installing dependencies..."
                // Example: sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo "Building the project..."
                // Example: sh 'npm run build'
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo "Archiving build artifacts..."
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
            cleanWs()
        }
    }
}
