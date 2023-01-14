pipeline {
    agent any
    stages {
        stage('build next app') {
            steps {
                sh 'docker build -t nextapp:dev .'
                sh 'docker run -p 3000:3000 --name nextapp -d nextapp:dev'
            }
        }
        stage('build nginx') {
            steps {
                sh 'cd nginx/'
                sh 'docker build -t nginxproxy:dev .'
                sh 'docker run -p 80:80 -p 443:443 -d nginxproxy:dev --name nginxproxy'
            }
        }
    }
}