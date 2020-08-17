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
                sh label: '', script: '''export name=vishnu
                export server=192.168.101.12
                spawn ssh $name@$server
                match_max 100000
                expect "*?assword:*"
                send -- "$pass\\r"
                send -- "\\r"
                interact'''
            }
        }
    }
}
