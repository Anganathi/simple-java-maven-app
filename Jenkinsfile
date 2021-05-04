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
      //  sh 'mvn deploy -DaltDeploymentRepository=com.comapny.app::default::http://localhost:8080/home/anganatn/deployment'
          sh 'mvn deploy'
      }
    }
  }
}
