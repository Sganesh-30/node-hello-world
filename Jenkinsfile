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
    }
}