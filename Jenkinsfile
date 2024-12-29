pipeline {
    agent any
    stages {
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }   
        stage ('Print Node Version') {
            steps {
                sh node -v
            }
        }
    }
}