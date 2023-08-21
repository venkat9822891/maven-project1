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
           deploy adapters: [tomcat9(credentialsId: '5c48791a-5d08-48a7-a598-8583f6e3ee21', path: '', url: 'http://172.31.32.217:9090/')], contextPath: 'devapps', war: '**/*.war'
         }
}
