pipeline {
    agent any

	
    stages {
        stage('Clone-Repo') {
	    	steps {
	        	git url: 'https://github.com/Aswini-202/gamukart.git',
				branch: 'master'
	    	}
        }
	stage('Build') {
		steps {
			sh 'mvn install'
		}
	}	
	 stage('Deploy') {
            steps {
                sshagent(credentials: ['your-ssh-credential-id']) {
                    sh 'scp -o StrictHostKeyChecking=no target/gamutkart.war root@10.0.0.10:/opt/tomcat/webapps
'
	    }
	}
    }
}
}
