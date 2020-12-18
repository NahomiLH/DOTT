pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          sh 'cd cidr_convert_api/go/'
          sh 'go build api.go convert.go'
        }

      }
    }

  }
  tools {
    go 'go-1.15.6'
  }
}