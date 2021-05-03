pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
         sh '/home/anganatn/Downloads/apache-maven-3.8.1/bin/mvn clean package'
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
