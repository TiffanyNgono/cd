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
        
        
          
    
    
}
}
