node {
    stage('Cont Download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
                            }
                            
    stage('Cont Build')     {
    sh 'mvn package'
                            }
    stage('Cont Deployment') {
    deploy adapters: [tomcat9(credentialsId: 'f681bf45-5c86-4d6d-8f56-01d68d33fd98', path: '', url: 'http://172.31.44.135:8080')], contextPath: '/newdevapp', war: '**/*.war'
                            }
                            
}
