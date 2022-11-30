pipleline{
  agent any
  environment{
    
  }
  tools{
    
  }
  stages{
    stage('Fetch code'){
      steps{
      git branch: 'ci-cd-deploy' , url:" "
      }
    }
    stage('Build Project'){
      steps{
        sh 'mvn install -DskipUnittest'
      }
    }
    stage('Test project'){
      steps{
        sh 'mvn test'
      }
    }
    stage('Quality project')
    {
      steps{
        sh 'mvn checkstyle:checkstyle'
      }
    }
    stage('Build Docker'){
      steps{
        script{
          dockerImage=docker.build 
        }
      }
    }
    stage('Push to Docker'){
      steps{
        script{
          dockerWithRegistry()
        }
      }
    }
      
       
