pipeline {
    agent { docker { image 'python:3.8.5' } }
    stages {
        stage('build') {
            steps {
		    withEnv(["HOME=${env.WORKSPACE}"]){
			    sh 'python --version'
			    sh 'pip install --user -r requirements.txt'
		    }
	    }
        }
        stage('test') {
            steps {
		    withEnv(["HOME=${env.WORKSPACE}"]){
			    sh 'pip install --user pytest==6.2.4'
			    sh 'python -m pytest ./test/test_addition.py'
		    }
	    }
	}
    }
}
