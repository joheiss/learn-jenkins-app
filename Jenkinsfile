pipeline {
    agent any

    stages {
        stage('Without Docker') {
            steps {
                sh '''
                    echo "No Docker!"
                    touch without-container.txt
                    ls -la
                '''
            }
        }
        stage('With Docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "With Docker!"
                    touch with-container.txt
                    ls -la
                    npm --version
                '''
            }
        }
        
    }
}
