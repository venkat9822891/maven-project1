node {
    stage('Cont.Download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
      }
	stage('Cont.Build') {
    sh 'mvn package'
      }
	stage('Cont.Deploy') {
    deploy adapters: [tomcat9(credentialsId: '36631b36-4171-4155-8fd5-882cc6aebd72', path: '', url: 'http://172.31.47.109:8080')], contextPath: '/realtimeapp', war: '**/*.war'
      }
}
