##modified
node {
    stage('cont.downloads') {
    git 'https://github.com/venkat9822891/maven-project1.git'
}
    stage('cont.build') {
    sh 'mvn package'
}
    stage('cont.deployment') {
    deploy adapters: [tomcat8(credentialsId: '9dd47a0c-1011-406f-957b-1b505e1455f7', path: '', url: 'http://43.204.30.155:8080/')], contextPath: '/dev-app', war: '**/*.war'
                   }
    
    
}
