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
        stage('minikube status') {
            steps {
                sh 'minikube status'
            }
        }
        stage('deploy') {
            steps {
                sh 'kubectl create -f test.yaml'
            }
        }
    }
}
