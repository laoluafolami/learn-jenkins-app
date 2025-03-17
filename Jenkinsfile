pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            args '--entrypoint=""'
        }
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                    test -f build/index.html
                    npm test
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step goes here!'
                // Example:
                // sh 'scp build/* user@server:/path/to/deploy/'
            }
        }
    }
}
