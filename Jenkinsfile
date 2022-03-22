node {
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
    deploy adapters: [tomcat8(credentialsId: '68659247-e3c3-4313-99cc-37e94f5bf716', path: '', url: 'http://172.31.12.12:8080')], contextPath: '/testingapp', war: '**/*.war'
     }
   stage('Cont.testing') 
     {
     git 'https://github.com/venkat9822891/Selenium-testcases.git'
     echo 'Testing complete'
     }
  stage('Cont.Delivery')
   {
     deploy adapters: [tomcat8(credentialsId: '2f644474-e2a3-4d08-8f26-08d0ec5dca31', path: '', url: 'http://172.31.38.214:8080')], contextPath: '/prodapp', war: '**/*.war'  
   }
}
