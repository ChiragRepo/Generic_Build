pipeline {
    agent any

    stages {

        stage('checkout code') {
            steps{
                //git pull 'https://github.com/ChiragRepo/JenkinsXMLParser.git'
                git url: 'https://github.com/ChiragRepo/JenkinsXMLParser.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building..'
                sh 'xbuild  JenkinsXMLParser.sln /p:Configuration=Release /p:OutputPath=bin/Release/JenkinsXMLParser'
                sh 'zip JenkinsXMLParser.zip, archive: false, dir: bin/Release/JenkinsXMLParser'
                sh 'curl -v -F "r=releases" -F "v=0.1-1" -F "p=zip" -F "file=JenkinsXMLParser.zip" -u admin:admin123 http://10.0.75.1:8081/repository/JenkinsXMLParser/'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}