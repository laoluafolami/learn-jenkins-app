pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('node:18-alpine').inside('--entrypoint=""') {
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
            }
        }
        stage('Test') {
            agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('node:18-alpine').inside('--entrypoint=""')
            steps {
                sh 'test -f build/index.html'
                npm test
                '''
            }
        }
    }
}
