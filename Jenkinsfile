pipeline{
    agent any
    stages{
           

      stage('Build'){
   
            steps{
                sh'''
                    docker build -t karthickcv/html_build:v1 . 
                '''
            }

        }

        stage('Deploy'){
            steps{
                sh'''
                    docker push karthickcv/html_build:v1 
                    '''
                }
            }
        }
    
}
