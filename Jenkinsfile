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
        stage("deploy in tomcat"){
            steps{
                sshagent(['tomcat_server']) {
                sh """
                     -o StrictHostKeyChecking=no
                    ssh ec2-user@172.31.45.158 /opt/tomcat8/bin/shutdown.sh
                    ssh ec2-user@172.31.45.158 /opt/tomcat8/bin/startup.sh
                   """ 
                }
            }
        }
    }
}