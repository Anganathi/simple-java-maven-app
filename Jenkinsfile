pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
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
        sh 'mvn clean deploy -Dmaven.test.skip=true'
      }
    }
  }
}
