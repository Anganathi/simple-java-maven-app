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
        echo 'Deploying stage'
<<<<<<< HEAD
        sh 'mvn deploy -DaltDeploymentRepository=snapshot-repo::default::file:~/my-app-v1'
=======
        sh 'mvn clean deploy'
>>>>>>> 4c4e9d1fd941cf93a443255a87ff00e445868a23
      }
    }
  }
}
