pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello World before version"'
                sh 'python --version'
                sh 'echo "Hello World after version"'
            }
        }
    }
}
