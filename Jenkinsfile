##modified second time modified
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
    deploy adapters: [tomcat8(credentialsId: 'a6a00475-2752-436e-878d-5db66ef166eb', path: '', url: 'http://172.31.42.115:8080')], contextPath: 'test', war: '**/*.war'
     }
   stage('Cont.testing') 
     {
     git 'https://github.com/venkat9822891/Selenium-testcases.git'
     echo 'Testing complete'
     }
  stage('Cont.Delivery')
   {
     deploy adapters: [tomcat8(credentialsId: 'cf6f23ff-9d14-4303-b0ee-d8e4118490ab', path: '', url: 'http://172.31.35.239:8080')], contextPath: 'prod', war: '**/*.war'  
   }
}
