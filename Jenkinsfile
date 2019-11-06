pipeline {
    agent any
    
    stages {
        stage('init') {
            steps {
                echo "Testing ..."
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
	    post {
	    	success {
			echo 'Now archiving...'
			archiveArtifacts artifacts: '**/target/.*war'
		}
	    }	
        }
        stage('Deploy') {
            steps {
                echo "Code deployed."
            }
        }
    }
}
