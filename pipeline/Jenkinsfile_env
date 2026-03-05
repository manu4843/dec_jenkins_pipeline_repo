pipeline {
    agent none
    environment {
        DOCKER_USER ='abcd4843'
        AWS_ACCESS_KEY ='7854126987415'
        
    }
    
    stages {
        stage ('STAGE1') {
            agent {label 'slave1'}
            steps {
                echo "DOCKER_USER :${DOCKER_USER}"
                echo "AWS_ACCESS_KEY :${AWS_ACCESS_KEY}"

                sh '''
                   env
                '''
            }
        }
    }
}
                
