pipeline{

   environment{
      
     registry = "karthickcv/own-deployment"
     registryCredential = 'dockerhub'
     dockerImage = ''
   } 

    agent any
    stages{
          

      stage('Cloning Git Repo'){
   
            steps{
                
                   git  'https://github.com/karthickcv/Html.git'

                
               
            }

        }
                
      
        stage('Build'){
            steps{
                sh'''
                   dockerImage =  docker.build registry + ":$BUILD_NUMBER"  
                   '''
                }
            }

        stage('Deploy'){
           
	    steps {

                 sh '''
                  docker.withRegistry ('',registryCredential) {
                   docker.push();
                    }		
                  '''
             }          
   
        }
   } 
 }
