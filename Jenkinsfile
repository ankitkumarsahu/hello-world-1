pipeline{
    agent any
    stages{
        stage("CLONE Code"){
            steps{
                git 'https://github.com/ankitkumarsahu/hello-world-1.git'
            }
        }
        stage("BUILD Code"){
            steps{
                sh "mvn clean install"
            }
        }
        stage("DEPLOY Code"){
            steps{
                sshagent(['deploy_user']) {
                sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@13.232.235.72:/opt/tomcat/webapps"
                }
            }
        }
    }
}
