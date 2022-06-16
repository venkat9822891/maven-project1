node 
{
stage('cont.download') 
{
git 'https://github.com/venkat9822891/maven-project1.git'
}
stage('Cont.Build')
{
sh 'mvn package'
}
stage('Cont.Deployment')
{
deploy adapters: [tomcat8(credentialsId: '8c937c35-1c02-459f-89c5-b72cf95e3d4c', path: '', url: 'http://3.110.31.217:8080/')], contextPath: '/from-jenkins-dev', war: '**/*.war'
}
stage('Cont.Testing')
{
git 'https://github.com/venkat9822891/Selenium-testcases.git'sh 'mvn package'
}
stage('Cont.Delivary')
{
deploy adapters: [tomcat8(credentialsId: '25cadf63-a3fd-4586-8414-d83d1a6ecdf6', path: '', url: 'http://65.2.38.214:8080/')], contextPath: '/from-jenkins-qa', war: '**/*.war'
}
}
