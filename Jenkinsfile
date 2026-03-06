pipeline {
    agent any
    parameter {
        booleanParam (name :'DEPLOY', description 'want to deploy to production') 
    }
    environment{
        CURRENT_ENV ='prod'
    }
    stages {
        
        stage('STAGE1 WHEN BRANCH'){
            // this stage will run when the branch is main
            when {
                branch 'main'
            }
            steps {
    
            echo "This  is  stage 1 running"
             sh '''
             sleep 5
             exit 1
             '''
            }
        }
        
        stage ('when environment'){
            // the stage will run when env value prod
            when{
               // not{

                environment name :'CURRENT_ENV' ,value :'prod'
               // }
            }
        
        steps {
            echo "This is final testing"
            sh 'sleep 5'
             }
       }
        stage ('when parameter'){
            // the stage will run when parameter value true
            when{
                //if you want to execute multiple condition use allof,anyone,not
                // not : not equal
                //want to check both branch and parameter
                //allof  {     // all the condition must be true
                anyone {    // if any one condition true
                branch 'main'
                 expression {params.DEPLOY ==true}
                }
            }
               
        }
        steps {
            echo "This is final testing"
            sh 'sleep 5'
            }
    }
    
}