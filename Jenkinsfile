pipeline {
    agent {
        kubernetes {
            yamlFile 'test.yaml'
   
            defaultContainer 'shell'
        }
    }

    stages {
        stage('test') {
            steps {
                echo 'this works'
            }
        }       
    }
}
