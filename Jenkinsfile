pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage ('Build'){
            steps{
                sh 'mvn clean package'
                 }
                       }
      
        stage ('Deploy to tomcat server')
        {
            steps{
                deploy adapters: [tomcat9(credentialsId: 'localhost', path: '', url: 'http://localhost:8081/')], contextPath: null, war: '**/*.war'
                 }

        }
    }
}
