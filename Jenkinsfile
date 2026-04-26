pipeline {
    // pre-build
     agent {
        label 'agent-node'  
     }
     options{
        timeout(time:10, unit: 'MINUTES')
        disableConcurrentBuilds()
       // retry(1)
     }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr jenkins', description: 'its me')
        text(name: 'BIO', defaultValue: '', description: 'enter info')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice (name: 'CHOICE', choices: ['one', 'two', 'Three'], description: 'pick somthing')
        password (name:'PASSWORD', defaultValue: 'SELECT', description: 'enter password')
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
              //  error 'pipeline failed'
            }
        }
        stage('print params'){
            steps{
                echo "Hello ${params.PERSON}"
                echo "Biography ${params.BIO}"
                echo "Toggle ${params.TOGGLE}"
                echo "Choice ${params.CHOICE}"
                echo "Password ${params.PASSWORD}"
            }
        }
        stage('Approval') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps{
                echo "hello, ${PERSON}, nice to meet you"
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