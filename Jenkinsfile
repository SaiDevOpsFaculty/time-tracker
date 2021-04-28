pipeline{
    agent any
    stages{
        stage("git checkout"){
            steps{
              git 'https://github.com/sahooashok709/time-tracker.git'
            }
        }
        stage("build in maven"){
            steps{
                sh "mvn clean package"
            }
        }
       /* stage("deploy in tomcat"){
            steps{
                sshagent(['jenkins_declarative']) {
                sh """
                    ssh -o StrictHostKeyChecking=no C:\JENKINS_HOME\workspace\jenkins_declarative_pipeline\web\target\myweb.war  ec2-user@172.31.45.158:/opt/tomcat8/webapps/
                    ssh ec2-user@172.31.45.158 /opt/tomcat8/bin/shutdown.sh
                    ssh ec2-user@172.31.45.158 /opt/tomcat8/bin/startup.sh
                   """ 
                }
            }
        } 
      */
    }
}