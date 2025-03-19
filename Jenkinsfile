node {
    stage('Clone repository') {
        git credentialsId: 'chanmin@futuregen.co.kr', url: 'https://github.com/echanim/jenkins.git'
    }

    stage('Build image') {
       dockerImage = docker.build("chanmin89/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
