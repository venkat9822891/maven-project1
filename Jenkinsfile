node {
    stage('cont.downloads') {
    git 'https://github.com/venkat9822891/maven-project1.git'
}
    stage('cont.Build') {
    sh 'mvn package'
}
    stage('cont.deployment') {
    deploy adapters: [tomcat8(credentialsId: '9dd47a0c-1011-406f-957b-1b505e1455f7', path: '', url: 'http://172.31.32.126:8080')], contextPath: '/dev-app', war: '**/*.war'
}
        stage('cont.delivery') {
          deploy adapters: [tomcat8(credentialsId: '5288ec19-ab0a-4ea9-8ffd-1058f3041f9f', path: '', url: 'http://172.31.35.249:8080')], contextPath: '/test-app', war: '**/*.war'
          }
}
