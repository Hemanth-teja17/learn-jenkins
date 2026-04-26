pipeline {
    // pre-build
     agent {
        label 'agent-node'  
     }
     options{
        timeout(time:10, unit: 'SECONDS')
        disableConcurrentBuilds()
        retry(1)
     }
 // build
    stages{    
        stage('Build'){
            steps{
                sh 'echo this is Build'
               // sh 'sleep 10'
            }
        }
        stage('Test'){
            steps{
                sh 'echo this is test'
            }
        }
        stage('Deploy'){
            steps{
                sh 'echo this is deploy'
                error 'pipeline failed'
            }
        }
        
    }

post{
    always{
        echo "this sections runs always"
        deleteDir()
    }
    success{
        echo " this section runs when pipeline success"
    }
    failure{
        echo "this section runs when pipeline failure"
    }
}
}