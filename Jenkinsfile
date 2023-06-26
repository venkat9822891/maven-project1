node {
    stage('Cont.Download') {
    git 'https://github.com/venkat9822891/maven-project1.git'
     }
    stage('Cont.Build') {
     sh 'mvn package'
     }
	stage('Cont.Deployment'){
	deploy adapters: [tomcat9(credentialsId: 'ff870275-2f9f-4d62-84ce-5d41182eddd0', path: '', url: 'http://13.233.129.8:9090')], contextPath: '/dev-test', war: '**/*.war'
	}

}
