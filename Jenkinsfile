node {
    stage('Cont Download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
                            }
                            
    stage('Cont Build')     {
    sh 'mvn package'
                            }
    stage('Cont Deployment') {
    deploy adapters: [tomcat9(credentialsId: 'test', path: '', url: 'http://172.31.37.184:8080')], contextPath: '/testapp', war: '**/*.war'
                            }
                            
}
