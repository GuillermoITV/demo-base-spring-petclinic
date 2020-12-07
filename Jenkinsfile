pipeline {
    agent { label 'master' }
    stages {
        stage('download') {
            steps {
                sh 'ls'
            }
        }
        stage('compile') {
            steps {
                sh  'sudo docker run -it --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean install'
            }
        }
         stage('upload to nexus') {
            steps {
                sh '''
                cd target
                '''
            }
        }
         stage('deploy') {
            steps {
                sh 'whoami'
            }
        }
    }
}
