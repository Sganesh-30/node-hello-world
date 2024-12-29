pipeline {
    agent any
    stages {
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        stage ('Print Node Js Version') {
            steps {
                sh 'node -v'
            }
        }
    }
}