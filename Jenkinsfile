pipeline{
<<<<<<< HEAD
  agent any
  stages{
    stage('Build Docker'){
      steps {
        sh 'docker pull maven:3.8.1'
      }
    }  
=======
  agent any 
 
  stages{
    stage('build Dockerfile') {
            steps {
                sh '''echo "FROM maven:3-alpine
                          RUN apk add --update docker openrc
                          RUN rc-update add docker boot" >/var/jenkins_home/workspace/Dockerfile'''
            }
         }

         stage('run Dockerfile') {
             agent{
                 dockerfile {
                     filename '/var/jenkins_home/workspace/Dockerfile'
                     args '--user root -v $HOME/.m2:/root/.m2  -v /var/run/docker.sock:/var/run/docker.sock'
                 }
             }
             steps {
                 sh 'docker version'
                 sh 'mvn -version'
                 sh 'java -version'
             }

         }

>>>>>>> 87ceeea1c122ce7a9a1b8b04dcaf2163f5aa05da
    stage('Build'){
      steps{
        sh 'mvn clean package'
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
    stage('Deploy'){
      steps{
        echo 'Deploying stage'
        sh 'mvn deploy'
      }
    }
  }
}
