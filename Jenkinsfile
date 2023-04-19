pipeline {
    agent {
        node { label 'AWS_Workstation'}
    }
    environment {
        SAMPLE_URL = "google.com"
        SSH         = credentials('AWS_workstation_ssh')
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
                echo "${SSH}"
            }
        }
    }

    post {
        always {
            echo 'I will say hello again'
        }
    }
}