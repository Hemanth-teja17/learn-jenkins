pipeline {
     agent {
        label 'AGENT-NODE'  // pre-build
     }
    stages{    // build
        stage('Build'){
            steps{
                sh 'echo this is Build'
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
            }
        }
        
    }

post{
    always{
        echo "this sections runs always"
    }
    success{
        echo " this section runs when pipeline success"
    }
    failure{
        echo "this section runs when pipeline failure"
    }
}
}