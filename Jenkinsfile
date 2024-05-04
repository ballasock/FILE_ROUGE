pipeline {
  agent any
  stages {
   
    stage ('test') {
      steps {
        bat 'docker ps -a'
      }
    }
    stage ('Run Docker Compose') {
      steps {
        bat 'docker-compose up  -d --build'
      }
    }
  }
  post {
    success {
      slackSend channel: 'groupe4', message: 'build success'
    }
    failure {
      slackSend channel: 'groupe4', message: 'build error'
    }
  }
}
