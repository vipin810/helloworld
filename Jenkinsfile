pipeline {
  agent any 
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
            deploy adapters: [tomcat9(path: '', url: 'http://ec2-3-145-118-39.us-east-2.compute.amazonaws.com:8090/')],contextPath: 'helloworld', onFailure: false, war: '../helloworld-0.0.1-SNAPSHOT.war'
        }
      }
    }
  }
}
