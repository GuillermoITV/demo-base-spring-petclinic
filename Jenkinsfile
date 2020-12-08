pipeline {
    agent { label 'nodo1' }
    stages {
        stage('download') {
            steps {
                sh '''
                ls
                '''
            }
        }
        stage('compile') {
            steps {
                sh  'docker run -i --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean install'
            }
        }
         stage('deploy') {
            steps {
                sh '''
                cd target
                cp petclinic.war /opt/tomcat/webapps/
                '''
            }
        }
         stage('sending email') {
            steps {
                sh 'echo "aqui enviaria un correo como notificacion"'
            }
        }
    }
}
