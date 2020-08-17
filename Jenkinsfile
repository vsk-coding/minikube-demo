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
                    sh 'ssh -l vishnu 192.168.101.12 vishnu -a'
                }
            }
        }
    }
}
