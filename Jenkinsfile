/* Use "make" in our own container image */
/* Requires the Docker Pipeline plugin */
pipeline {
    agent {
        dockerfile {
            filename 'Dockerfile'
            dir 'pipeline'
        }
    }
    stages {
        stage('build') {
            steps {
                sh 'make build'
            }
        }
    }
}
