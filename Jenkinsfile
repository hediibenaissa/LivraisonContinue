pipeline
{
    agent any
    stages {
    stage('Build'){
            steps{
                script{
                    sh "ansible-playbook -vvvv /var/lib/jenkins/workspace/myapp/ansible/build.yml -i ansible/inventory/host.yml "
                }
            }
        }
       stage('docker'){
            steps{
                script{
                    sh "ansible-playbook -vvvv /var/lib/jenkins/workspace/myapp/ansible/docker.yml -i ansible/inventory/host.yml "
                }
            }
        }
      stage('Docker login') {

                                         steps {
                                          sh 'echo "login Docker ...."'
                   	sh "docker login -u hediibenaissa -p M123iphone"
                               }  }
      stage('docker registry'){
            steps{
                script{
                    sh "ansible-playbook -vvvv /var/lib/jenkins/workspace/myapp/ansible/docker-registry.yml -i ansible/inventory/host.yml "
                }
            }
        }
    }
} 
