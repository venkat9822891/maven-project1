node('node1') {
    stage('Cont.Download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
                            }
    stage('Cont.Build') {
    sh 'mvn package'
                         }
    stage('Cont.Deployment') {
    deploy adapters: [tomcat8(credentialsId: '9d9bb938-6a7b-4272-9259-249db7d0b5ca', path: '', url: 'http://172.31.32.126:8080')], contextPath: '/dev-app', war: '**/*.war'
                         }
}
