pipeline {
    agent any

    stages {
        stage('checkout build script') {
            git url: 'https://github.com/ChiragRepo/Generic_Build.git'
            sh 'git clean -fdx; sleep 4;'
        }

        stage('checkout code') {
            git url: 'https://github.com/ChiragRepo/JenkinsXMLParser.git'
            sh 'git clean -fdx; sleep 4;'
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