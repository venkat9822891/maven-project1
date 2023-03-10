node('slv1') {
    stage('Cont.Download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
    }
    stage('Cont.Building') {
    sh 'mvn package'
    }
    stage('Cont.Deployment'){
    deploy adapters: [tomcat8(credentialsId: 'qa', path: '', url: 'http://172.31.36.247:8080')], contextPath: '/app-qa', war: '**/*.war'
    }
}
