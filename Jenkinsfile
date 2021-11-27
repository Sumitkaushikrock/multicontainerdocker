pipeline {
    agent none
    stages {
        stage('Fetch git repo and build docker image') {
            agent { label 'docker-agent-1' }
            steps {
                sh 'git clone https://github.com/Sumitkaushikrock/multicontainerdocker.git'
                sh 'docker -H tcp://docker.for.mac.localhost:3375 build -t sumitkaushik445/client ./client'
                sh 'docker -H tcp://docker.for.mac.localhost:3375 build -t sumitkaushik445/nginx ./nginx'
                sh 'docker -H tcp://docker.for.mac.localhost:3375 build -t sumitkaushik445/server ./server'
                sh 'docker -H tcp://docker.for.mac.localhost:3375 build -t sumitkaushik445/worker ./worker'
                sh 'docker login -u sumitkaushik445 -p 94251@Sumit'
            }
        }
    }
}