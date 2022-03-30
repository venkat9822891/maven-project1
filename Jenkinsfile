##modified second time modified
node('slv1')
 {
    stage('ContDownload')
 {
    git 'https://github.com/venkat9822891/maven-project1.git'
}

   stage('ContBuild')
 {
   sh 'mvn package'
}

   stage('ContDeployment')
 {
   deploy adapters: [tomcat8(credentialsId: '42489c7c-4385-4f32-8ff1-41dddf81541b', path: '', url: 'http://172.31.33.5:8080')], contextPath: '/test', war: '**/*.war'
}
   stage('Conttesting')
 {
    git 'https://github.com/venkat9822891/Selenium-testcases.git'
    echo "testingcases completed"
}
   stage('ContDelivery')
 {
   deploy adapters: [tomcat8(credentialsId: 'prod', path: '', url: 'http://172.31.39.20:8080')], contextPath: '/production', war: '**/*.war'
}
}
