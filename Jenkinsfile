pipeline {
    agent { label 'master' }
    stages {
        stage('download') {
            steps {
                sh '''
                ls
                chmod 777 script.sh
                ./script.sh
                '''
            }
        }
        stage('compile') {
            steps {
                sh  'ls'
            }
        }
         stage('upload to nexus') {
            steps {
                sh 'ls'
            }
        }
         stage('deploy') {
            steps {
                sh 'whoami'
            }
        }
    }
}
