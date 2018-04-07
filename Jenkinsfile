pipeline {
    agent any

    stages {

        stage('checkout code') {
            git pull 'https://github.com/ChiragRepo/JenkinsXMLParser.git'
            //sh 'git clean -fdx; sleep 4;'
        }

        stage('Build') {
            steps {
                echo 'Building..'

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