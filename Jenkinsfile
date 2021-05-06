pipeline {
    agent { docker { image 'python:3.8.5' } }
    stages {
        stage('build') {
            steps {
		    withEnv(["HOME=${env.WORKSPACE}"]){
			    sh 'python --version'
			    sh 'python -m pip uninstall pip -y'
			    sh 'pip install --user -r requirements.txt'
		    }
	    }
        }
        stage('test') {
            steps {
		    withEnv(["HOME=${env.WORKSPACE}"]){
			    sh 'pytest ./test/test_addition.py'
		    }
	    }
	}
    }
}
