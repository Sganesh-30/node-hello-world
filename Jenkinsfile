pipeline {
    agent any

    tools {
        nodejs 'NodeJS-234'
        SonarQube 'SonarQube-620'
    }

    environment {
        SONARQUBE_ENV = 'SonarQube'
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
                sh 'npx mocha test/**/*.js'
            }
        }
        stage ('Code Coverage') {
            steps {
                sh 'npm run coverage'
            }
        }
    }
}