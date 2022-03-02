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
             when {
                branch 'main'
            }
             input {
                message "Can we Proceed?"
                ok "Yes"
                submitter "padmaraju"
                parameters {
                    string(name: 'PERSON', defaultValue: 'padmaraju', description: 'Member')
                }
            }
            steps {
              deploy adapters: [tomcat9(credentialsId: '7e1845d4-6dcb-46ac-8a89-016ae3b21963', path: '', url: 'http://3.235.54.23:8080/')], contextPath: 'sampletomcatwebapp', war: '**/*.war'  
           }
            
        }
        
    }
}
