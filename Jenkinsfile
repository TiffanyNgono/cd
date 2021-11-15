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
        
        
          
    
    
}
}
