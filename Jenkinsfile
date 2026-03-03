pipeline {
    agent any
    stages {
        stage ('STAGE1') {
            steps {
                echo "This is the stage1"
                sh 'sleep 5'
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

        }   
            }
}
