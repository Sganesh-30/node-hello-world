pipeline {
    agent any

    tools {
        nodejs 'NodeJS-234'
    }

    stages {
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        stage ('Print NodeJs and NPM Version') {
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
        }
        stage ('Installing Dependencies') {
            steps {
                sh 'npm install'
                sh 'npm install --save-dev mocha'
                sh 'npm install --save-dev nyc'
            }
        }   
        stage ('Run Unit Test') {
            steps {
                sh 'npx mocha test/**/*.js'
                sh 'npx nyc npm test'
            }
        }
        stage ('Code Coverage') {
            steps {
                sh 'npm run coverage'
            }
        }
        stage ('SonarQube Code Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    withCredentials([string(credentialsId: 'SonarQube-620', variable: 'SoanrQube-Token')]) {
                        sh '''    
                            sonar-scanner \
                            -Dsonar.projectKey=node-hello-world \
                            -Dsonar.sources=. \
                            -Dsonar.host.url=http://3.85.37.125:9000 \
                            -Dsonar.token=sqp_6609aebd7cb0c59de63889cb68d233a0d8fcb9f5
                        '''
                    }
                
                }
            }
        }
    }
}


