pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
        sh 'mvn -B -DskipTests clean package'
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
    stage('Deliver'){
      steps{
        sh 'deliver.sh'
      }
    }
  }
}
