pipeline{
  agent any 
 
  stages{
    stage('Build dockerfile'){
      steps{
         sh 'docker pull maven:3.8.1'
        // args '-v /root/.m2:/root/.m2'   
        }
    }
    stage('Build'){
      steps{
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
        sh 'docker --version'
      }
      post{
        always{
          junit '/target/surefire-report/*.xml'
        }
      }
    }
    stage('Deliver'){
      steps{
        sh './jenkins/scripts/deliver.sh'
      }
    }
  }
}
