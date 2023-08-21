node {
    stage('Download code from git') 
	     {
           git 'https://github.com/venkat9822891/maven-project1.git'
         }
    stage('Convert artifacts') 
	     {
           sh 'mvn package'
         }
	stage('Deploy code into container') {
           deploy adapters: [tomcat9(credentialsId: 'c196ae0d-c9fa-4436-bb44-26ab990bd52c', path: '', url: 'http://172.31.38.232:7070')], contextPath: '/qaapps', war: '**/*.war'
         }
}
