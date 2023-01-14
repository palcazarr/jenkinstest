pipeline {
    agent {
        dockerfile true
    }
    stages {
        stage('Install') {
            steps {
                sh 'npm install -g pnpm'
                sh 'pnpm install'
            }
        }
        stage('build') {
            steps {
                echo 'Done!'
            }
        }
    }
}