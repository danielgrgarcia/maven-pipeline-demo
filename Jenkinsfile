pipeline {
	agent any

	stages {
		stage("build") {
			steps {
				sh "mvn --version"
				sh "maven clean install"
			}
		}
	}

	post {
		always {
			cleanWs()
		}
	}
}