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
        stage('Hi') {
            steps {
               echo "hi , how are you"
            }
        }
    }
}
