pipeline {
    agent { 
        label 'cent'
    }
    stages {
        stage('build') {
            steps {
                sh 'docker build -t simple-website .'
            }
        }
        stage('run') {
            steps {
                sh 'docker run -d -p 80:80 simple-website'
            }
        }
        stage('test') {
            steps {
                sh 'curl localhost:80'
            }
        }
    }
}