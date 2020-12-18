pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        dir(path: 'cidr_convert_api/go/') {
          sh '''ls
pwd
go version
go get github.com/gorilla/mux
go get github.com/pkg/errors
go get github.com/stretchr/testify/assert
#goop install
'''
          sh '''go build api.go convert.go
ls'''
        }

      }
    }

    stage('Test') {
      steps {
        dir(path: 'cidr_convert_api/go/')
        sh 'go test convert.go'
      }
    }

  }
  tools {
    go 'go-1.15.6'
  }
}