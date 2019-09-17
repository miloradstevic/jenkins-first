pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('build') {
            steps {
                sh 'echo "Editet through Visual Studio Code"'
                sh 'python --version'
                sh 'echo "Commited through git cli"'
            }
        }
    }
}
