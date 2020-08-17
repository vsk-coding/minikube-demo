pipeline {
    agent any

    stages {
        stage('test') {
            steps {
                echo 'this works'
            }
        }
        stage('connect') {
            steps {
                sshagent(['minikube']) {
                    sh 'ip a'
                }
            }
        }
    }
}
