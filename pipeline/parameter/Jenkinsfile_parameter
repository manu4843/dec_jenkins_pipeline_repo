pipeline {
    agent none
    parameters{
        string(name :'NAME',defaultValue:'',description :'please tell your name')
        booleanParam (name : 'SKIP_TEST',description :'want to skip test runs to direct deploy')
        choice(name :'BRANCH',choices :['master','staging','prod'])
    }
    
    stages {
        stage ('STAGE1') {
            agent {label 'slave1'}
            steps {
                echo "NAME :${params.NAME}"
                echo "SKIP_TEST :${params.SKIP_TEST}"
                echo "BRANCH TO DEPLOYE: ${params.BRANCH}"

                sh '''
                echo "NAME :${NAME}"
                echo "SKIP_TEST :${SKIP_TEST}"  
                echo "BRANCH TO DEPLOYE :${BRANCH}"
                '''
            }
        }
    }
}
                
