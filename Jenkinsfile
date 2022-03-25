pipeline {
    agent any
    tools { 
        maven 'maven' 
        
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage ('deploy') {
            
           
             input {
                message "Can we Proceed?"
                ok "Yes"
                submitter "padmaraju"
                parameters {
                    string(name: 'PERSON', defaultValue: 'padmaraju', description: 'Member')
                }
            }
            
            
        }
        
    }
}
