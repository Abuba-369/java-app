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
	stage ('Deploy') {
            sshagent(['tomcat-dev']) {
                sh 'scp StrictHostKeyChecking=no target/*.war root@192.168.1.228:/root/tomcat9/webapps' 
            }
        }
    }
}
}
