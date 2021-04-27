pipeline{
    agent any
    stages{
        stage("git checkout"){
            steps{
              git 'https://github.com/sahooashok709/time-tracker.git'
            }
        }
        stage(build in maven){
            steps{
                sh "mvn clean package"
            }
        }
    }
}