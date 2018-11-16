pipeline {
    agent any
    stages {
        stage ('checkout') {
            steps {
		checkout scm
            }
        }
          stage ('Build') {
             steps {
                sh '${m2_home}/bin/mvn -f java-sample-app/pom.xml clean install' 
            }
	    
        }
    stage ('Deploy') {
             steps {
	        // sh 'ssh -o StrictHostKeyChecking=no root@puporigin.zippyops.com uptime'
                sh 'scp -o StrictHostKeyChecking=no root@puporigin.zippyops.com /var/lib/jenkins/workspace/whattodo/java-sample-app/target/java-sample-app-1.0.0.war root@192.168.1.3:/root/tomcat/webapps'
		sh 'puppet agent -t'     
            }
	    
        }
    }
	
}

