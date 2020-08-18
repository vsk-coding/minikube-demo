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
                    def val = sh './minikube-status.sh'
                    if(  val == 'host: Running') {
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
