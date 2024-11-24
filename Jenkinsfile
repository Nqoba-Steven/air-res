pipeline {
    agent {
        label 'docker'
    }

    stages { 
        stage('Docker node test') {
            agent {
                docker {
                    label 'docker'
                    image 'node:21-alpine'
                    args '--name docker-node'
                    reuseNode true
                }
            }
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
    }
}