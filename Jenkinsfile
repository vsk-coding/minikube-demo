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
                sh label: '', script: 'minikube status'
            }
        }
        stage('deploy app') {
            steps {
               sh 'kubectl apply -f Deployment.yml'
            }
        }
    }
}
