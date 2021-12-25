properties([pipelineTriggers([githubPush()])])
 
pipeline {
    /* specify nodes for executing */
    agent any
 
    stages {
        /* checkout repo */
        stage('Checkout SCM') {
         
         steps {
                script{
                   try{
                      sh(script: "rm -r testJPGitRepo", returnStdout: true)    
                   }catch (Exception e) {
                       echo 'Exception occurred: ' + e.toString()
                   }                   
                   sh(script: "git clone https://github.com/rambusnis/testJPGitRepo.git", returnStdout: true)
                   sh(script: "ls -ltr", returnStatus: true)
                }
            }
            
        }
         stage('Do the deployment') {
            steps {
                echo ">> Run deploy applications "
            }
        }
    }
 
    /* Cleanup workspace */
    post {
       always {
           deleteDir()
       }
   }
}
