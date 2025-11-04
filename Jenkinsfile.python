/* Sample from https://www.jenkins.io/doc/pipeline/tour/hello-world/ */
/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'python:3.14.0-alpine3.22' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
    }
}
