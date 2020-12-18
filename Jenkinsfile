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
        dir(path: 'cidr_convert_api/go/') {
          sh '''set +e
go test -coverprofile=coverage.xml
ls
--
curl -s . https://codecov.io/ -t CODECOV_TOKEN'''
        }

      }
    }

    stage('QA') {
      steps {
        dir(path: 'cidr_convert_api/go') {
          sh '''echo "Quality Analysis"
go get github.com/golangci/golangci-lint/cmd/golangci-lint@v1.33.0
golangci-lint run api.go convert.go'''
        }

      }
    }

  }
  tools {
    go 'go-1.15.6'
  }
  environment {
    CODECOV_TOKEN = 'a0aced14-5a3c-43d4-8a80-85621f9d3f1d'
  }
}