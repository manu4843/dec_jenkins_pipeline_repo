pipeline {
    agent any
    parameters {
        booleanParam (name :'DEPLOY', description :'want to deploy to production') 
    }
    environment{
        CURRENT_ENV ='prod'
    }
    stages {
        stage ('CHECKOUT'){
            checkout ([$class :'GitSCM'
            (branches: [[name: '*/main']],
               extensions: [], 
               userRemoteConfigs: [[credentialsId: 'hp-git', url: 'https://github.com/manu4843/dec_jenkins_pipeline_repo.git']])
            )]

        }
        
        stage('STAGE1 WHEN BRANCH MAIN'){
            // this stage will run when the branch is main
            when {
                expression {
                    return env.GitSCM-BRANCH =='origin/main'
                }
            }
            steps {
    
            echo "This  is  stage 1 running"
             sh '''
             pwd
             ls -lrt
             sleep 5
             
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
            sh '''
            pwd
            ls -lrt
            sleep 5
            '''
             }
       }
        stage ('when parameter'){
            // the stage will run when parameter value true
            when{
                //if you want to execute multiple condition use allof,anyof,not
                // not : not equal
                //want to check both branch and parameter
                //allOf  {     // all the condition must be true
                anyOf {    // if any one condition true
                branch 'main'
                 expression {params.DEPLOY ==true}
                }
            }
            steps{
                echo "environment variables are declared inside the pipeline block "
            }
               
        }
        stage ('FINAL STAGE') {
        steps {
            echo "This is final testing"
            sh 'sleep 5'
            }
        }    
    }
    
}