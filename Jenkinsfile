pipeline {
	environment {
		JAVA_TOOL_OPTIONS = "-Duser.home=/home/jenkins"
	}
	agent {
		dockerfile {
			args "-v /tmp/maven:/home/jenkins/.m2 -e MAVEN_CONFIG=/home/jenkins/.m2"
		}
	}

	stages {
		stage("build") {
			steps {
				sh "ssh -V"
				sh "mvn --version"
				sh "mvn clean install"
			}
		}
	}

	post {
		always {
			cleanWs()
		}
	}
}