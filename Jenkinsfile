pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
         sh 'mvn clean package'
      }
    }
    stage('Compile'){
      steps{
        sh 'mvn compile'
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
        sh 'mvn deploy -DskipTests -DaltDeploymentRepository=dd863a66-c8f4-4115-9a05-b3f86eafa475::default::http://localhost:8080/home/anganatn/maven-deployments'
      //    sh 'mvn deploy'
      }
    }
  }
}
