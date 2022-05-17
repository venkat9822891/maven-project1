###Modified
node()
{
stage('Cont.Download') 
{
    git 'https://github.com/venkat9822891/maven-project1.git'
}
stage('Cont.Build') 
{
    sh 'mvn package'
}
stage('Cont.Deployment')
{
deploy adapters: [tomcat8(credentialsId: 'd48ce171-66f5-4dee-87cd-6c973a829c4a', path: '', url: 'http://3.110.40.155:8080/')], contextPath: '/myapptest', war: '**/*.war'
}
stage('Cont.Testing')
{
git 'https://github.com/venkat9822891/Selenium-testcases.git'
}
stage('Cont.Deployment') 
{
    deploy adapters: [tomcat8(credentialsId: 'd48ce171-66f5-4dee-87cd-6c973a829c4a', path: '', url: 'http://3.109.3.209:8080/')], contextPath: '/myappqa', war: '**/*.war'
}
}

