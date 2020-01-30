pipeline{
    agent any
    environment{
        DOCKER_TAG = getDockerTag()
    }
    stages{
        stage('Build Docker Image'){
            steps{
                sh "docker build -t dhoni/nodeapp:${DOCKER_TAG}"
            }
        }
    }
}

def getDockerTag(){
    def tag = sh script: 'git rev-parse HEAD', restunStdout: true
    return tag
}
