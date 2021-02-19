pipeline{
    agent any
    stages{
           

      stage('Build'){
            agent{
                    dockerfile true
                }
            steps{
                sh'''
                    ./docker build -t karthickcv/html_build:v1 Dockerfile 
                '''
            }

        }

        stage('Deploy'){
            steps{
                sh'''
                    ./docker push karthickcv/html_build:v1 
                    '''
                }
            }
        }
    
}
