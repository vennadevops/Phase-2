node {
   stage('zip-pckage') {
   
        sh "git archive --format=zip --output=docker-engine.zip HEAD:Docker/DockerEngine/"
        sh "git archive --format=zip --output=docker-compose.zip HEAD:Docker/DockerCompose/"
        sh "git archive --format=zip --output=ansible.zip HEAD:Ansible/"
   
   }
}
