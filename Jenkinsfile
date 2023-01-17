pipeline {
    environment{
        REDIRECTPORT = 3000
        HOSTNAME = 192.168.64.3
    }
    agent any
    stages {
        stage('build next app') {
            steps {
                sh 'docker build -t nextapp:dev .'
                sh 'docker run -p 3000:3000 -d --rm nextapp:dev'
            }
        }
        stage('build nginx') {
            steps {
                docker.build('nginxproxy:dev:', '-f /nginx/Dockerfile \
                    --build-arg HOSTNAME="$HOSTNAME" \
                    --build-arg REDIRECTPORT="$REDIRECTPORT" .')
                sh 'docker run -d -p 80:80 -p 443:443 --rm nginxproxy:dev'
            }
        }
    }
}