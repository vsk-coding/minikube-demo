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
                script {
                    def val = sh 'minikube status'
                    def min-ok ='minikube
                                type: Control Plane
                                host: Running
                                kubelet: Running
                                apiserver: Running
                                   kubeconfig: Configured'
                    if(  val == min-ok) {
                        echo 'yes'
                    }
                    else {
                        echo 'no'
                    }
                }
            }
        }
    }
}
