pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo "Building"
                sh 'python --version'
                sh 'terraform-compliance -h'
                sh 'terraform -v'
            }
        }
        stage('test') {
            steps {
                echo "Testing"
                sh 'python --version'
                /*input "Continue?"*/
            }
        }
        stage('deploy') {
            steps {
                echo "Deploying"
                sh 'python --version'
            }
        }
    }
    post {
        always {
            echo 'Cleaning up the temporary workspace'
            deleteDir() /* clean up our workspace */
        }
        success {
            echo 'Pipeline execution successful'
        }
        failure {
            echo 'Pipeline execution failed'
            mail to: 'milorad.stevic@live.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
        }
        unstable {
            echo 'Pipeline execution successful, but one or more tests failed, marking this version unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
