pipeline {

    agent any
 
    stages {
        
        stage('Build') {
            steps {
                echo 'Building..'
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
