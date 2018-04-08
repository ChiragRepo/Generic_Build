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
                echo env.BUILD_NUMBER
                sh 'xbuild  JenkinsXMLParser.sln /p:Configuration=Release /p:OutputPath=bin/Release/JenkinsXMLParser'
                sh "zip JenkinsXMLParser + "${env.BUILD_NUMBER}".zip archive: false dir: bin/Release/JenkinsXMLParser"
                //sh 'curl -v -u admin:admin123 --upload-file JenkinsXMLParser.zip  http://10.0.75.1:8081/repository/jenkinsxmlparser/JenkinsXMLParser.zip'
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