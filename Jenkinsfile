pipeline{
    agent any
    stages{
        stage("git checkout"){
            steps{
              git 'https://github.com/sahooashok709/time-tracker.git'
            }
        }
        stage("deploy in tomcat"){
            steps{
                sshagent(['tomcat_server']) {
                sh """
                    'ssh -o StrictHostKeyChecking=no -l cloudbees 172.31.45.158 uname -ec2-user'
                    ssh ec2-user@172.31.45.158 /opt/tomcat8/bin/shutdown.sh
                    ssh ec2-user@172.31.45.158 /opt/tomcat8/bin/startup.sh
                   """ 
                }
            }
        }
    }
}