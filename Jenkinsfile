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
            }
        }   
        stage ('Run Unit Test') {
            steps {
                sh 'npm test'
            }
        }
    }
}