node {
    stage('Clone repository') {
        checkout scm
    }
    stage('Build image') {
       app = docker.build("nginx/")
    }
    stage('Push to registry'){
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
    }
}