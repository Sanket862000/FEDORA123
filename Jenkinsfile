pipeline {
    agent any
    parameters {
  choice choices: ['DEV', 'QA', 'UAT'], description: 'this choice parameter', name: 'ENVIRONMENT'
}
    stages {
        stage ('chekout') {
            steps {
              git 'https://github.com/Sanket862000/REDHAT.git'   
            }
        }
        stage ('build') {
            steps {
                  sh 'mvn install'
            }
        }
        stage ('Deployment') {
            steps {
                script {
                        if ( "${env.ENVIRONMENT}" == 'QA' ){
        	sh 'cp target/FEDORA123.war /home/sanket/Documents/Devops/apache-tomcat-9.0.93/webapps'
        	echo "deployment has been done on QA!"
			 }
			else if ( "${env.ENVIRONMENT}" == 'UAT' ){
    		sh  'cp target/FEDORA123.war /home/sanket/Documents/Devops/apache-tomcat-9.0.93/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"                   
                }
            }
        }
    }
}
