pipeline {
    agent any

    stages {

        stage('checkout code') {
            steps{
                cleanws
                git url: 'https://github.com/ChiragRepo/JenkinsXMLParser.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building..'
                echo BUILD_NUMBER
                sh 'xbuild  JenkinsXMLParser.sln /p:Configuration=Release /p:OutputPath=bin/Release/JenkinsXMLParser'
                sh 'zip JenkinsXMLParser_\"$BUILD_NUMBER\".zip archive: false dir: bin/Release/JenkinsXMLParser'
                sh 'curl -v -u admin:admin123 --upload-file JenkinsXMLParser_\"$BUILD_NUMBER\".zip  http://10.0.75.1:8081/repository/jenkinsxmlparser/JenkinsXMLParser_\"$BUILD_NUMBER\".zip'
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