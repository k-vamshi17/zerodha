pipeline {
    agent any

    tools {
        nodejs 'node18'  // The name you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/k-vamshi17/zerodha.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install -g @angular/cli'
                sh 'npm install'
            }
        }

        stage('Build Angular App') {
            steps {
                sh 'ng build --configuration production'
            }
        }

        stage('Deploy') {
            steps {
                // Example: Copy to a folder on server (adjust to your setup)
                sh 'cp -r dist/zerodha/* /var/www/html/'
            }
        }
    }
}
