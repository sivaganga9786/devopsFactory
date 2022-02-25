pipeline {
    agent any
    tools { 
        maven 'maven3' 
        
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
       // stage ('Build') {
       //     steps {
        //      deploy adapters: [tomcat9(credentialsId: 'tomcatdeployer', path: '', url: 'http://52.66.208.18:8080')], contextPath: 'SimpleTomcatWebApp', onFailure: false, war: '**/*.war'  
       //     }
            
     //   }
        
    }
}
