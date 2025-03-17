pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "without docker"
                    ls -la
                    touch container-no.txt
                    '''
            }
        }
        stage('w/ docker') {
            steps {
                sh '''
                    ls -la
                    touch container-yes.txt
                    '''
                script {
                    docker.image('node:18-alpine').inside {
                       
                        sh 'echo "with docker"'
                        sh 'npm --version'
                    }
                }
            }
        }
    }
}
