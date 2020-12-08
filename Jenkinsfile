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
                sh  'ls'
            }
        }
         stage('deploy') {
            steps {
                sh '''
               cd /home/cloud_user/workspace/melleva/target/
               cp petclinic.war /home/cloud_user
               docker run -d -p 8080:8080 -p 8009:8009 -v /home/cloud_user:/opt/tomcat/webapps dordoka/tomcat
               ls
               pwd
               ./script.sh
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
