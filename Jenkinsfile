pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          sh 'cidr_convert_api/go/Dockerfile'
          sh 'sudo docker build -t gom .'
        }

      }
    }

  }
  tools {
    go 'go-1.15.6'
  }
}