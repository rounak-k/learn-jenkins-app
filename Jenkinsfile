pipeline {
    agent any 
        stages{
            stage('Build'){
                agent {
                    docker{
                        image 'node:18-alpine'
                        reuseNode true  // this is used to provide one common workspace for the pipeline
                    }
                }
                steps{
                    sh '''
                        la -la
                        node --version
                        npm --version
                        npm ci
                        npm run build
                        ls -la 
                        echo 'changes'
                    '''
                }
            }
        }
    
}