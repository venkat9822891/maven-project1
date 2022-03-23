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
    deploy adapters: [tomcat8(credentialsId: '21757c38-48bd-4060-878b-8e5f217f117d', path: '', url: 'http://172.31.45.139:8080/')], contextPath: '/testapp', war: '**/*.war'
       }
       stage('Cont.Testing') 
       {
    git 'https://github.com/venkat9822891/Selenium-testcases.git'
        }
        stage('Cont.Deployment') 
       {
    deploy adapters: [tomcat8(credentialsId: '21757c38-48bd-4060-878b-8e5f217f117d', path: '', url: 'http://172.31.45.139:8080/')], contextPath: '/prodapp', war: '**/*.war'
        }
}
