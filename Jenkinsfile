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
                sh 'nuget config -Set repositoryPath=bin/Release/JenkinsXMLParser'
                sh 'nuget pack -IncludeReferencedProjects -properties Configuration=Release'
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