pipeline {
    agent any
    environment {
        ENV_URL = "aws.com"
    }
    stages {
        stage('stage one') {
            steps {
                sh " echo stage one "
                sh " echo the website is ${ENV_URL} "
            }
        }
        stage('stage two') {
            environment {
                instance_type = "t2.micro"
            }
            steps {
                sh ''' 
                echo stage two
                type of instance is ${instance_type} '''

            }
        }
        
    }
}               