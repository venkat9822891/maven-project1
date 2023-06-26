node {
    stage('Cont.Download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
     }
    stage('Cont.Build') {
     sh 'mvn package'
     }
	stage('Cont.Deployment'){
	deploy adapters: [tomcat9(credentialsId: 'f85c25ef-d1cd-447b-be0a-8f8e095d3396', path: '', url: 'http://13.126.204.87:8080')], contextPath: '/dev-test', war: '**/*.war'
	}

}
