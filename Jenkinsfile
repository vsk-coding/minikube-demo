pipeline {
    agent {
        label 'minikube-slave'
    }

    stages {
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
        stage('test') {
            steps {
                sh 'minikube service hello-node'
            }
        }
    }
}
