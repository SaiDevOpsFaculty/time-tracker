pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        git 'https://github.com/Debasish96/time-tracker.git'
        sh '/opt/maven/apache-maven-3.6.3/bin/mvn compile'
      }
    }
	stage('test') {
	  post {
        always {
          junit 'target/surefire-reports/**/*.xml'
        }
      }
      steps {
	    sh '/opt/maven/apache-maven-3.6.3/bin/mvn test'
	  }
	}
	stage('package') {
	  steps {
	    sh '/opt/maven/apache-maven-3.6.3/bin/mvn clean package'
	  }
	}
  }
}
