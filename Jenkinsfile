pipeline {
    agent any
    stages {
        
        stage('STAGE1'){
            steps {
                catchError(buildResult :'SUCCESS',stageResult :'FAILURE'){
                echo "Thi is  stage 1 running"
                sh '''
                sleep 5
                exit 1
                '''
                }
            }
        }
        stage ('PARALLEL TESTING'){
            parallel {
                stage ('WINDOWS TESTING'){
            steps {
                echo "This is windows testing running"
                sh 'sleep 5'
            }
                }
            stage ('MACOS TESTING'){
                steps{
                    echo "This is Macos testing running"
                    sh 'sleep 5'
                }
            }
          }
        }
    stage ('FINAL STAGE'){
        steps {
            echo "This is final testing"
            sh 'sleep 5'
             }
       }
    }
}