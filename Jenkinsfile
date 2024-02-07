pipeline {
    agent any
    environment{
        PATH="/opt/maven/bin:$PATH"
    }

    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/supreethb/hello-world.git'
            }
        }
        stage('maven') {
            steps {
               sh "mvn package"
            }
        }
        stage('deployment') {
            steps {
                sshagent(['deployment']) {
            sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@54.165.74.250:/opt/tomcat/webapps"
           }
        
            }
        }
}
