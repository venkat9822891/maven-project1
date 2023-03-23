node {
    stage('Cont.Download') 
    {
    git 'https://github.com/venkat9822891/maven-project1.git'
    }
    stage('Cont.Build') {
    sh 'mvn package'
    }
    stage('Cont.Deploy') {
    deploy adapters: [tomcat9(credentialsId: '36631b36-4171-4155-8fd5-882cc6aebd72', path: '', url: 'http://ec2-13-127-164-216.ap-south-1.compute.amazonaws.com:8080')], contextPath: '/test-app', war: '**/*.war'
    }
    
}
