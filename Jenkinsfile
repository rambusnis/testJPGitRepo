
String TRAGET_INSTANCE_ID="768a6e27-4ce8-4da3-8452-984f0ba674c4"

pipeline { 
    agent any 
    
   
    stages {
        stage('Initial-Connect-ExpImp-CreateNewInstance') { 
            steps { 
                script{
                sh """
                   echo "${TRAGET_INSTANCE_ID}" > /var/lib/jenkins/newconnectInstance.txt
                """
                //build job: 'AWS-Connect-ExpImp-CreateNewInstance',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]                     
                }
            }
        }
        stage('Connect-Queue-Sync'){
            steps {
                script{
                sh"""
                 cat /var/lib/jenkins/newconnectInstance.txt
                """
                //build job: 'AWS-Connect-ExpImp-CreateNewInstance',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]  
                }

                
            }
        }
        stage('RoutingProfile-Sync') {
            steps {
                 script{
                    sh"""
                    cat /var/lib/jenkins/newconnectInstance.txt
                    """
                //build job: 'AWS-Connect-RoutingProfile-Sync',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]  
                }
            }
        }
        
        stage('QuickConnect-Sync') {
            steps {
                
                 script{
                //build job: 'AWS-Connect-QuickConnect-Sync',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]  
                 sh"""
                    cat /var/lib/jenkins/newconnectInstance.txt
                    """

                     
                }
            }
        }
        
        stage('Users-Sync') {
            steps {
                
                script{
                //build job: 'AWS-Connect-Users-Sync',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]  
                 sh"""
                    cat /var/lib/jenkins/newconnectInstance.txt
                    """
                }
            }
        }
        
    }
}
