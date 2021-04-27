pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        git 'https://github.com/lerndevops/samplejavaapp.git'
        sh '/opt/maven/apache-maven-3.6.3/bin/mvn compile'
      }
    }
	stage('package') {
	  steps {
	    sh '/opt/maven/apache-maven-3.6.3/bin/mvn clean package'
	  }
	}
  }
}
