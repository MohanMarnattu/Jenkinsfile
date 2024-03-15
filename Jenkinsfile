node('built-in') {
    stage('ContDownload') 
    {
    git 'https://github.com/intelliqittrainings/maven.git' 
        
    }
   stage('ContBuild') 
    {
     sh 'mvn package'
        
    }
       stage('ContDeployment') 
    {
      deploy adapters: [tomcat9(credentialsId: 'c4c2d9b9-d1bf-48b7-b192-7dff3c16888b', path: '', url: 'http://172.31.82.237:8080')], contextPath: 'path1', war: '**/*.war'
          
    }
     stage('ContTesting') 
    {
     git ' https://github.com/intelliqittrainings/FunctionalTesting.git'
     sh 'java -jar /var/lib/jenkins/workspace/Scripted-Pipeline/testing.jar'
    }
    stage('ContDelivary') 
    {
    deploy adapters: [tomcat9(credentialsId: 'c4c2d9b9-d1bf-48b7-b192-7dff3c16888b', path: '', url: 'http://172.31.86.49:8080')], contextPath: 'path2', war: '**/*.war'
    
    }
}
