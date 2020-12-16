pipeline {
    agent { docker { image 'golang' } }
    stages {
        stage('build') {
            steps {
                shell 'go version'
            }
        }
    }
}
