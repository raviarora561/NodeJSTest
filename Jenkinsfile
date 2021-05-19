node { 

  stage 'checkout scm'
  checkout scm

  stage 'Docker build Node API'
  dir("${env.WORKSPACE}/node-hello") {
    docker.build('raviarora561/nodejstest')
    }

  stage 'Docker push API'
  docker.withRegistry('', 'RaviDockerhub') {
    docker.image('raviarora561/nodejstest').push("latest")
  }

  stage('Remove Unused docker image') {
  sh ("echo y | docker system prune")
  }
}
