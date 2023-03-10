node('slv1') {
    stage('Cont.Download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
    }
    stage('Cont.Building') {
    sh 'mvn package'
    }
    stage('Cont.Deployment'){
    deploy adapters: [tomcat8(credentialsId: 'Test-Env', path: '', url: 'http://172.31.46.16:8080')], contextPath: '/app-dev', war: '**/*.war'
    }
}
