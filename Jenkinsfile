pipeline {

    stages { 
        stage('Docker node test') {
            agent {
                docker {
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