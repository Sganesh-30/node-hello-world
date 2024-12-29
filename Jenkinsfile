pipeline {
    agent any

    tools {
        nodejs 'Nodejs-234'
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
            }
        }
        stage ('Installing Dependencies') {
            steps {
                sh 'npm install'
            }
        }
    }
}