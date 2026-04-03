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
        stage('Deploy'){
            steps{
                bat 'if not exist C:deployments1 mkdir C:\\deployments1'
                bat 'copy target\\demo-1.0-SNAPSHOT.jar  C:\\deployments1'
            }
        }
        stage('Run Application'){
            steps{
                bat 'java -jar C:\\deployments1\\demo-1.0-SNAPSHOT.jar com.example.Main'
            }
        }
    }
}