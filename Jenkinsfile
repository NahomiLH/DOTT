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
cd /DOTT/cidr_convert_api/go
docker build -t gom .
docker run -ti -p 8000:8000 gom'''
      }
    }

  }
}