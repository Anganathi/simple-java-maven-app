pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
	 def mvnHome = tool name: 'maven3.8.1', type: 'maven'
         sh '$mvnHome/bin/mvn clean package'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
      }
    }
    stage('Deploy'){
      steps{
        echo 'Deploying stage'
        sh 'mvn deploy'
      }
    }
  }
}
