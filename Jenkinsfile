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
        stage('deploy hello minikube') {
            steps {
                sh 'kubectl create -f test.yaml'
            }
        }
        stage('test deployment') {
            steps {
                sh 'minikube service hello-node'
            }
        }
        stage('cleanup') {
            steps {
                sh 'kubectl delete service hello-node'
                sh 'kubectl delete deployment hello-node'
            }
        }
    }
}
