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
        stage('Compile'){
            steps{
                bat 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                bat 'mvn test'
            }
        }
        stage('Build/package'){
            steps{
                bat 'mvn clean package'
            }
        }
        stage('Package'){
            steps{
                bat 'mvn package'
            }
        }
        stage('Release(Artifact check)'){
            steps{
                bat 'dir target'
                bat 'jar tf target/demo-1.0-SNAPSHOT.jar'
            }
        }
    }
}