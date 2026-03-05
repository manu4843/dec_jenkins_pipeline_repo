pipeline {
    agent none
    parameters{
        string { name :'NAME',description :'please tell your name'}
        boolean {name : 'SKIP_TEST',description :'want to skip test runs to direct deploy'}
        choice {name :'BRANCH',choice :['master','staging','prod']}
    }
    
    stages {
        stage ('STAGE1') {
            agent {label 'slave1'}
            steps {
                echo "NAME :${params.NAME}"
                echo "SKIP_TEST :${params.SKIP_TEST}"
                echo "BRANCH : ${params.BRANCH}"
            }
        }
    }
}
                
