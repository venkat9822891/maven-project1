## Edited
node('master')
{
    stage('ContinuousDownload') 
    {
         git 'https://github.com/venkat9822891/maven-project1.git'
    }
    stage('ContinuousBuild') 
    {
         sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/BuildPipeline-Scripted/webapp/target/webapp.war ubuntu@172.31.2.73:/var/lib/tomcat8/webapps/testenv.war'
    }
    stage('ContinuousTesting')
    {
        git 'https://github.com/venkat9822891/Selenium-testcases.git'
        sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/Apple-ReleaseIpad-Bp/testing.jar'
    }
     stage('ContinuousDelivery')
    {
        input message: 'Waiting for Approval from the Architect', submitter: 'Ramani'
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@:/var/lib/tomcat8/webapps/prodenv.war'
    }
    
    
}

