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
ls
cd cidr_convert_api/go
#goop install

'''
      }
    }

  }
}