pipeline {
      agent any
    tools {
        go 'go-1.15.6'
    }
    environment {
        GO1156MODULE = 'on'
    }
    stages {
        stage('Compile') {
            steps {
                sh 'go build api.go'
                sh 'go build convert.go'
                             
            }
        }
        stage('Test') {
            environment {
                CODECOV_TOKEN = credentials("a0aced14-5a3c-43d4-8a80-85621f9d3f1d)
            }
            steps {
                sh 'go test ./... -coverprofile=coverage.txt'
                sh "curl -s https://codecov.io/bash | bash -s -" bash <(curl -s https://codecov.io/bash)
            }
        }
        stage('Code Analysis') {
            steps {
                sh 'curl -sfL https://install.goreleaser.com/github.com/golangci/golangci-lint.sh | bash -s -- -b $GOPATH/bin v1.12.5'
                sh 'golangci-lint run'
            }
        }
    }
}
