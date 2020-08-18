pipeline {
    agent {
        label 'minikube-slave'
    }

    stages {
        stage('test') {
            steps {
                echo 'this works'
            }
        }
        stage('connect') {
            steps {
                sh label: '', script: 'ip a | grep inet'
            }
        }
        stage('minikube run') {
            steps {
                try {
                    sh 'minikube start'
                }
                catch(error) {
                    sh 'minikube status'
                }
            }
        }
    }
}
