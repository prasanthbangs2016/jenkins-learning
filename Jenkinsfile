pipeline {
    agent {
        node { label 'AWS_Workstation'}
    }

    stages {
        stage('Hai') {
            steps {
                echo "Hello World"
            }
        }
    }

    post {
        always {
            echo 'I will say hello again'
        }
    }
}