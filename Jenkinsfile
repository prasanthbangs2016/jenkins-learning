//pipeline {
//    agent {
//        node { label 'AWS_Workstation'}
//    }
//    options { disableConcurrentBuilds() }
//
//    environment {
//        SAMPLE_URL = "google.com"
//        SSH         = credentials('AWS_workstation_ssh')
//    }
//
//    triggers { pollSCM('* * * * *') }
//
//    //least used option
//    tools { maven 'MAVEN' }
//
//    parameters {
//        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//
//        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//
//        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//
//        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//
//        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//    }
//
//    stages {
//        stage('Hai') {
//            steps {
//                echo "Hello World"
//
//                echo "Hello ${params.PERSON}"
//
//                echo "Biography: ${params.BIOGRAPHY}"
//
//                echo "Toggle: ${params.TOGGLE}"
//
//                echo "Choice: ${params.CHOICE}"
//
//                echo "Password: ${params.PASSWORD}"
//            }
//
//
//        }
//
//        stage('Hello') {
//            steps {
//                echo "Hello Hello"
//                echo "URL = ${SAMPLE_URL}"
//                echo "${SSH}"
//            }
//        }
//
//        stage('Input') {
//            input {
//                message "Should we continue?"
//                ok "Yes, we should."
//                submitter "alice,bob"
//                parameters {
//                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//                }
//            }
//            steps {
//                echo "PERSON = ${PERSON}"
//            }
//        }
//
//    }
//
//    post {
//        always {
//            echo 'I will say hello again pkp1'
//        }
//    }
//}

//pipeline {
//    agent any
//
//    stages {
//        stage('one') {
//            steps {
//                echo 'one'
//            }
//        }
//
//        stage('two') {
//            steps {
//                echo 'two'
//            }
//        }
//    }
//}


//pipeline {
//    agent any
//
//    parameters {
//        choice(name: 'DEPLOY_TO', choices: ['', 'DEV', 'STAGE', 'PROD'], description: 'choose the environment')
//
//    }
//
//    stages {
//        stage('DEV') {
//            when {
//                environment name: 'DEPLOY_TO', value: 'DEV'
//            }
//            steps {
//                echo 'one'
//            }
//        }
//
//        stage('PROD') {
//            when {
//                environment name: 'DEPLOY_TO', value: 'PROD'
//            }
//            steps {
//                echo 'two'
//            }
//        }
//    }
//}


//pipeline {
//    agent any
//
//    parameters {
//        choice(name: 'DEPLOY_TO', choices: ['', 'DEV', 'STAGE', 'PROD'], description: 'choose the environment')
//
//    }
//
//    stages {
//        stage('DEV') {
//            when {
//                environment name: 'DEPLOY_TO', value: 'DEV'
//            }
//            steps {
//                echo 'one'
//            }
//        }
//
//        stage('PROD') {
//            when {
//                expression { BRANCH_NAME ==~ /(production|staging)/ }
//                anyOf {
//                    environment name: 'DEPLOY_TO', value: 'PROD'
//                    environment name: 'DEPLOY_TO', value: 'STAGE'
//                }
//            }
//            steps {
//                echo 'two'
//            }
//        }
//    }
//}


pipeline {
    agent any

    parameters {
        booleanParam(name: 'DEPLOY', defaultValue: true, description: 'DEPLOY')

    }

    stages {
        stage('DEV') {
            when {
                return DEBUG_BUILD
                //return if this is false
            }
            steps {
                echo 'one'
            }
        }

        stage('PROD') {
            when {
                environment name: 'DEPLOY_TO', value: 'PROD'
            }
            steps {
                echo 'two'
            }
        }
    }
}





