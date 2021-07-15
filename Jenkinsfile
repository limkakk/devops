node('master') 
{
  stage('ContinuousDownload') 
  {
    git 'https://github.com/selenium-saikrishna/maven.git'
  } 
  stage('ContinuousBuild') 
  {
    sh 'mvn package'
  }
  stage('ContinuousDeployment') 
  {
    sh 'scp /var/lib/jenkins/workspace/scripted/webapp/target/webapp.war ec2-user@172.31.12.231:/opt/tomcat/apache-tomcat-8.5.68/webapps/qaenv.war'
  }
}
