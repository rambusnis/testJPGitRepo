import groovy.json.JsonSlurper;
import groovy.json.JsonSlurperClassic ;
import groovy.json.JsonOutput;

@NonCPS
def jsonParse(def json) {
    new groovy.json.JsonSlurperClassic().parseText(json)
}

def toJSON(def json) {
    new groovy.json.JsonOutput().toJson(json)
}

def toSTRINGTOJSON(def json) {
    new groovy.json.JsonOutput().toJson(json)
}

def toJSON2(def json) {
    JsonOutput.prettyPrint(JsonOutput.toJson(json))
}

def TRAGET_INSTANCE_ID=""

pipeline { 
    agent any 
    stages {
        stage('Initial-Connect-ExpImp-CreateNewInstance') { 
            steps { 
                script{
                    //build job: 'AWS-Connect-ExpImp-CreateNewInstance'                  
                    echo "hello"

                    sh'''
                    #!/bin/bash
                    dldir="$HOME/ramtestlinux/5.x"
                    
                    [ ! -d "$dldir" ] && mkdir -p "$dldir"
                    
                    '''
                }
            }
        }
        stage('Connect-Queue-Sync'){
            steps {
                script{

                    

                    TRAGET_INSTANCE_ID= sh(script: 'cat /var/lib/jenkins/newconnectInstance.txt', returnStdout: true).trim()
                    //build job: 'AWS-Connect-ExpImp-CreateNewInstance',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]  
                }
            }
        }
        stage('RoutingProfile-Sync') {
            steps {
                 script{
                    TRAGET_INSTANCE_ID= sh(script: 'cat /var/lib/jenkins/newconnectInstance.txt', returnStdout: true).trim()
                    //build job: 'AWS-Connect-RoutingProfile-Sync',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]  
                }
            }
        }
        
        stage('QuickConnect-Sync') {
            steps {
                 script{
                    TRAGET_INSTANCE_ID= sh(script: 'cat /var/lib/jenkins/newconnectInstance.txt', returnStdout: true).trim()                     
                    //build job: 'AWS-Connect-QuickConnect-Sync',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]  
                }
            }
        }
        
        stage('Users-Sync') {
            steps {
                script{
                TRAGET_INSTANCE_ID= sh(script: 'cat /var/lib/jenkins/newconnectInstance.txt', returnStdout: true).trim()
                //build job: 'AWS-Connect-Users-Sync',parameters: [string(name: 'TRAGET_INSTANCE', value:TRAGET_INSTANCE_ID)]  
                }
            }
        }
        
    }
}
