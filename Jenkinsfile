pipeline {
    agent any
    stages {
        stage('build next app') {
            steps {
                sh 'docker build -t nextapp:dev .'
                sh 'docker run -p 3000:3000 -d --rm nextapp:dev --name nextapp:dev'
            }
        }
        stage('build nginx') {
            steps {
                sh 'docker build --file ./nginx/Dockerfile -t nginxproxy:dev .'
                sh 'docker run -d -p 80:80 -p 443:443 --rm nginxproxy:dev --name nginxproxy:dev '
            }
        }
    }
}