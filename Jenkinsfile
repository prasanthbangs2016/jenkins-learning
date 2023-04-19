pipeline {
    agent {
        node { label 'AWS_Workstation'}
    }
    options { disableConcurrentBuilds() }

    environment {
        SAMPLE_URL = "google.com"
        SSH         = credentials('AWS_workstation_ssh')
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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