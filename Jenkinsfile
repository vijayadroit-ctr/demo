pipeline {
    agent any
    tools{
        jdk 'JDK17'
        maven 'Maven3'
    }
    stages{
        stage('Checkout code'){
            steps{
                git branch:'main', url:'https://github.com/vijayadroit-ctr/demo.git'
            }
        }
    }
}