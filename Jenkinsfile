pipeline {
	environment {
		JAVA_TOOL_OPTIONS = "DUser.home=/var/maven"
	}
	agent {
		docker {
			image "maven:3.6.0-jdk-13"
			args "-v /tmp/maven:/var/maven/.m2 MAVEN_CONFIG=/var/maven/.m2"
		}
	}

	stages {
		stage("build") {
			steps {
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