pipeline {
    agent any
    environment {
        ENV_URL = "aws.com"
    }
    parameters {
        string (name: 'component', defaultvalue: 'mongodb' )
        choice (name: 'env', choices:['dev', 'prod'])
    }
    stages {
        stage('stage one') {
            steps {
                sh '''echo stage one
                echo the website is ${ENV_URL}'''
            }
        }
        stage('stage two') {
            environment {
                instance_type = "t2.micro"
                ENV_URL = "azure.com"
            }
            steps {
                sh '''echo stage two
                echo type of instance is ${instance_type}
                echo website is ${ENV_URL}'''

            }
        }
        
    }
}               