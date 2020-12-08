pipeline {
    agent { label 'nodo1' }
    stages {
        stage('download') {
            steps {
                sh 'ls'
            }
        }
        stage('compile') {
            steps {
                sh  'docker run -i --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean install'
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
