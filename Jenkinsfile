pipeline {
  agent any
  stages {
    stage('Dockerbuild') {
      steps {
        script {
          cd DOTT/cidr_convert_api/go/
          sh 'sudo docker build -t gom .'
          sh 'sudo docker run -ti -p 8000:8000 gom'
        }

      }
    }

  }
}