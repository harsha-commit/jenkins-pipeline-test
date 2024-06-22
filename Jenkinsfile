pipeline {
    agent { label 'AGENT-1' }
    options {
        timeout(time: 1, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    environment { 
        PROJECT = 'expense'
        DEPLOY_TO = 'dev'
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Im in Build"'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Im in Test"'
            }
        }
        stage('Parameters') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }
        stage('Environments'){
            steps{
                sh 'env | grep DEPLOY_TO'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Im in Deploy"'
            }
        }
    }
    post {
        success { 
            echo 'Well done!'
        }
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
