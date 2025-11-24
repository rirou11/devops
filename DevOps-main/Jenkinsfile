pipeline {
    agent any

    tools {
        jdk 'JDK21'      // make sure this name exists in Jenkins → Manage Jenkins → Global Tool Configuration
        maven 'Maven3'   // same here: tool name must match your Maven installation name
    }

    stages {
        stage('Checkout') {
            steps {
                echo '📥 Cloning repository...'
                git branch: 'main', url: 'https://github.com/Jizel14/DevOps.git'
            }
        }

        stage('Build') {
            steps {
                echo '⚙️ Running Maven build...'
                sh 'mvn clean compile -U'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed — check console output for details.'
        }
    }
}
