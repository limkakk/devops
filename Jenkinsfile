node('master') 
{
  {
    environment{
     JAVA_HOME = "/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.282.b08-1.amzn2.0.1.x86_64"
     PATH = "/opt/apache-maven-3.8.1/bin:$PATH"
   }
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
