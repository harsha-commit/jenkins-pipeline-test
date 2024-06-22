pipeline {
    agent { label 'AGENT-1' }
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
        stage('Deploy') {
            steps {
                sh 'echo "Im in Deploy"'
            }
        }
    }
}
