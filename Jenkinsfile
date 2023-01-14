pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                sh 'apt-get install nodejs npm'
                sh 'npm install -g pnpm'
                sh 'pnpm install'
            }
        }
        stage('build') {
            steps {
                sh 'pnpm run build'
            }
        }
        stage('launch') {
            steps {
                sh 'node node .next/standalone/server.js'
            }
        }
    }
}