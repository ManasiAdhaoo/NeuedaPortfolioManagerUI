pipeline {
  agent any
 
  stages {

    stage('Build and run container') {
      steps {
        sh "docker stop uiapp || echo 'App not running'"
        sh "docker container rm uiapp || echo 'No container to remove'"
        sh "docker rmi ui/app:latest || echo 'No image to remove'"
        sh "docker build -t ui/app ."
        sh "docker run -d -p 8081:80 --name uiapp ui/app"
      }
    }
  }
}
