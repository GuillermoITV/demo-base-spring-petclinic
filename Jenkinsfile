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
                sh  'docker run -i --rm --privileged --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean install'
            }
        }
         stage('deploy') {
            steps {
                sh '''
               whoami
               cp /home/cloud_user/workspace/melleva/target/petclinic.war /home/cloud_user
               docker ps -l
               docker run -d -p 80:8080 --privileged --name prueba dordoka/tomcat
               docker cp /home/cloud_user/petclinic.war prueba:/opt/tomcat/webapps
               ls
               pwd
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
