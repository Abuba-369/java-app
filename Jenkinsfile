pipeline {
    agent any
	tools {
    maven 'M3'
  }
	
    stages {
        stage ('checkout') {
            steps {
		checkout scm
            }
        }
          stage ('Build') {
             steps {
                sh '${m2_home}/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/M3/bin/mvn -f java-sample-app/pom.xml clean install' 
            }
	    
        }
   // stage ('Deploy') {
     //        steps {
	       //  sh 'ssh -o StrictHostKeyChecking=no root@puporigin.zippyops.com uptime'
		// sh 'ssh root@puporigin.zippyops.com -l  -o "PubkeyAuthentication=no"'
		// sh 'PermitRootLogin yes'
       //         sh 'scp  /var/lib/jenkins/workspace/whattodo/java-sample-app/target/java-sample-app-1.0.0.war root@puporigin.zippyops.com:/opt/tomcat/webapps'
		// sh 'puppet agent -t' 
		 
         //   }
	    
      //  }
    // stage ('change values') {
       //      steps {
          //      sh 'puppet agent -t' 
         //   }
	    
      //  }
    
    }
	
}

