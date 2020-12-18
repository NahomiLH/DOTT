pipeline {
  agent any
  tools {
        go 'go-1.15.6'
    }
  stages {
    stage('Build') {
      steps {
        script {
          sh 'cd cidr_convert_api/go/'
          sh 'sudo docker build -t gom .'

        }

      }
    }

  }
}
