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

stage('Install') {
             steps{
                script{
                    sh "sudo npm install"
                }
            }
        }
stage ('Build') {
	
			steps {
			
			sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"
	
			}


	}
stage('Docker') {
             steps{
                script{
                    sh "sudo ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml"
                }
            }
        }
stage('docker_registry') {
    steps{
    script {
        sh "ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/host.yml "
          }
       }
    }
 }
 }
