pipeline {
    agent any
    
    stages {
        stage ('STAGE1') {
            steps {
                echo "This is the stage1"
                
                sh ''' 
                sleep 5
                echo "This is a linux command"
                '''
            }
        }
        stage ('STAGE2') {
            steps{
                echo "This is Stage2"
                sh '''
                #!/bin/bash
                pwd
                ls -lrt
                sleep 5
                '''
            }

        }    }
}
