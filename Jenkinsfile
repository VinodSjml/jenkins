pipeline {
    agent any
    environment {
        ENV_URL = "aws.com"
    }
    parameters {
        string (name: 'component', defaultValue: 'mongodb' )
        choice (name: 'env', choices:['dev', 'prod'])
    }
    tools {
        maven 'mvn-3.9.6'
    }
    stages {
        stage('parallel'){
            parallel{
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
                    echo website is ${ENV_URL}
                    mvn -v'''
                    }
                }
         
             }
        
        }
        stage(sequentital){
            stage('sq one'){
                steps {
                    sh "echo sq 1"
                }    
            }
            stage('sq two'){
                steps {
                    sh "echo sq 2"
                }
            }

        }
    }
}              