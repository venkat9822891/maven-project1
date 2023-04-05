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
    deploy adapters: [tomcat9(credentialsId: '114aa7a4-d531-4676-b9bc-d8dcabe6bc8c', path: '', url: 'http://172.31.46.59:9090')], contextPath: '/new-deployment', war: '**/*.war'
       }
}
