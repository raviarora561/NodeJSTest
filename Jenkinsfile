node { 

  stage 'checkout scm'
  checkout scm

  stage 'Docker build Node API'
  dir("${env.WORKSPACE}/nodejs-test") {
    docker.build('DockerhubUsername/equibizprodapi')
    }

  stage 'Docker push API'
  docker.withRegistry('', 'DockerHub') {
    docker.image('DockerhubUsername/nodejs-test').push("latest")
  }

  stage('Remove Unused docker image') {
  sh ("echo y | docker system prune")
  }
}
