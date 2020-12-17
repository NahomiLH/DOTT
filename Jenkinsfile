pipeline {
  agent {
    docker {
      image 'golang'
    }

  }
  stages {
    stage('Config') {
      steps {
        sh '''git version
go version
cd cidr_convert_api/go
#goop install
'''
      }
    }

  }
}