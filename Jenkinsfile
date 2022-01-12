pipeline { 
    agent any 
    
    
    stages {
        stage('Initial-Connect-ExpImp-CreateNewInstance') { 
            steps { 
                script{
                build job: 'AWS-Connect-ExpImp-CreateNewInstance'
                }
            }
        }
        stage('Connect-Queue-Sync'){
            steps {
                script{
                build job: 'AWS-Connect-ExpImp-CreateNewInstance'
                }

                
            }
        }
        stage('RoutingProfile-Sync') {
            steps {
                
                 script{
                build job: 'AWS-Connect-RoutingProfile-Sync'
                }
            }
        }
        
        stage('QuickConnect-Sync') {
            steps {
                
                 script{
                build job: 'AWS-Connect-QuickConnect-Sync'
                }
            }
        }
        
        stage('Users-Sync') {
            steps {
                
                 script{
                build job: 'AWS-Connect-Users-Sync'
                }
            }
        }
        
    }
}
