pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
         sh 'mvn -DskipTests clean install'
      }
    }
    stage('Deploy'){
      steps{
        echo '========Deploying stage========'
        sh 'mvn install tomcat7:deploy'
      //    sh 'mvn deploy'
      }
    }
  }
}
