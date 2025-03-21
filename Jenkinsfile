node {
    stage('Clone repository') {
        git credentialsId: 'docker-access', url: 'https://github.com/echanim/jenkins.git'
    }

    stage('Build image') {
       dockerImage = docker.build("chanmin89/mydiary-front:1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
