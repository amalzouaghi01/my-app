pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[credentialsId: '9e86d403-f421-4488-8345-004c3f1efa61',
                            url: 'https://github.com/amalzouaghi01/my-app.git']]])
                }
            }
        }
 }
 }
