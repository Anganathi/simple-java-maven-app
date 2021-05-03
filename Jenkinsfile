pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
	tool name: 'maven3.8.1' type: 'maven'
        sh 'mvn clean package'
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
