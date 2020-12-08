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
               whoami
               sudo -n systemctl restart docker 
               cd /home/cloud_user/workspace/melleva/target/
               cp petclinic.war /home/cloud_user
               docker run -d -p 80:8080 --name prueba dordoka/tomcat
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
