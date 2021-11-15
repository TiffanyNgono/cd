pipeline {

    agent any


      stages {
          stage ('pull') {
                steps {
                   script{
                       checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                           userRemoteConfigs: [[
                               credentialsId: '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',
                               url: 'https://github.com/TiffanyNgono/project-cd.git']]])

                
            }
        }     
       
    }

stage ('Install') {
              steps{
                 script{
                     sh "sudo npm install"
                }
            }
        }
        
        stage ('build') {
              steps {
                 script{
                     sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
                   }
              }
          }
        
        
          
    
 stage ('docker') {
              steps {
                 script{
                     sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml "
                   }
              }
          }    
}
}
