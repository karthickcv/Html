pipeline {
  agent { label 'docker' }
  
      
    stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/karthickcv/Html.git'
      }
    }

      
    stage('Build') {
      steps {
        sh 'docker build -t karthickcv/own-deployment .'
        sh 'docker build -t karthickcv/own-deployment .'
      }
    }
    stage('Publish') {
      when {
        branch 'master'
      }
      steps {
        withDockerRegistry([ credentialsId: "dockerhub", url: "" ]) {
          sh 'docker push karthickcv/own-deployment'
         
        }
      }
    }
  }
}
