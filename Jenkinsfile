pipeline {
    agent {
        node { label 'AWS_Workstation'}
    }
    environment {
        SAMPLE_URL = "google.com"
    }

    stages {
        stage('Hai') {
            steps {
                echo "Hello World"
            }
        }

        stage('Hello') {
            steps {
                echo "Hello Hello"
                echo "URL = ${SAMPLE_URL}"
            }
        }
    }

    post {
        always {
            echo 'I will say hello again'
        }
    }
}