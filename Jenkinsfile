##modified
node() 
{
    stage('Cont.Download') 
      {
        git 'https://github.com/venkat9822891/maven-project1.git'
       }
    stage('Cont.Build') 
      {
    sh 'mvn package'
       }
    stage('Cont.Deployment') 
     {
    deploy adapters: [tomcat8(credentialsId: '3f09ca4c-3eb9-4dea-a467-c8a06e8436f4', path: '', url: 'http://172.31.45.215:8080')], contextPath: '/scriptedapp', war: '**/*.war'
     }
}
