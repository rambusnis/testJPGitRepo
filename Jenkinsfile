pipeline {

    agent any

    environment { 
        CC = 'clang'
    }
 
    stages {
        
        stage('Build') {
            
            environment { 
                DEBUG_FLAGS = '-g'
            }
            steps {
                echo 'Building..'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                sh 'printenv'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    /* stage('Checkout SCM') {
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

    } */
 
}
