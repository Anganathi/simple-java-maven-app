pipeline{
  agent any
  stages{
    stage('Build Docker'){
      steps {
        sh 'docker pull maven:3.8.1'
      }
    }  
    stage('Build'){
      steps{
        sh 'mvn clean package'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
      }
      post{
        always{
          junit '/target/surefire-report/*.xml'
        }
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
