node('built-in') 
{
    stage('Continues Download') 
    {
     git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('Continues Build') 
    {
     sh 'mvn package'
    }
    stage('Continues Deployment') 
    {
     deploy adapters: [tomcat9(credentialsId: '96fbb076-fbc9-49b9-829e-e2758b74f1a5', path: '', url: 'http://172.31.13.2:8080')], contextPath: 'testsp-1', war: '**/*.war'
    }
      stage('Continues Testing') 
    {
     git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
     sh 'java -jar /home/ubuntu/.jenkins/workspace/Scripted-1/testing.jar'
    }
    stage('Continues Deployment') 
    {
     deploy adapters: [tomcat9(credentialsId: '96fbb076-fbc9-49b9-829e-e2758b74f1a5', path: '', url: 'http://172.31.5.246:8080')], contextPath: 'prodsp-1', war: '**/*.war'
    }
}
