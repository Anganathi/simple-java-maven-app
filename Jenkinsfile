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
        echo '========Deploying stage========'
        sh 'mvn deploy -DskipTests -DaltDeploymentRepository=my-app::default::http://localhost:8080/home/anganatn/maven-deployments'
      //    sh 'mvn deploy'
      }
    }
  }
}
