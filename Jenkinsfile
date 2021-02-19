pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                agent{
                    dockerfile true
                }

                script{
                    docker build -t karthickcv/html_build:v1 Dockerfile 
                }
            }

        }

        stage('Deploy'){
            steps{
                script{
                    docker push karthickcv/html_build:v1 
                }
            }
        }
    }
}