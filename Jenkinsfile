##modified
node {
    stage('cont.download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
}
    stage('cont.build') {
    sh 'mvn package'
}
    stage('cont.deployment') {
    deploy adapters: [tomcat8(credentialsId: '3f09ca4c-3eb9-4dea-a467-c8a06e8436f4', path: '', url: 'http://http://43.204.30.155:8080')], contextPath: '/devops-app', war: '**/*.war'
}
    stage('cont.deployment-test'){
        deploy adapters: [tomcat8(credentialsId: 'f552cd72-0ce9-41b3-8f38-f814d5846b42', path: '', url: 'http://172.31.35.249:8080')], contextPath: '/devops-app', war: '**/*.war'
                                }
    
}
