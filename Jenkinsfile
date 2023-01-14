pipeline {
    agent {
        docker { image 'node:16.13.1-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
        stage('Install') {
            steps {
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