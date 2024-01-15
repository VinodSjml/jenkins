pipeline {
    agent any
    environment {
        ENV_URL = "aws.com"
    }
    stages {
        stage('stage one'){
            steps {
                sh ''' 
                echo stage one
                and the website is ${URL} 
                '''
            }
        }
        stage('stage two'){
            environment{
                instance_type = "t2.micro"
            }
            steps {
                sh ''' 
                echo stage two
                and type of instance is ${instance_type} 
                '''

            }
        }
        
    }
}               