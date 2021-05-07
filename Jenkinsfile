pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
         sh 'mvn -DskipTests clean install'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
      }
    }
    stage('Deploy'){
      steps{
        echo '========Deploying stage========'
        sh 'mvn tomcat7:deploy'
      //    sh 'mvn deploy'
      }
    }
  }
}
