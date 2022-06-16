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
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './stopByport.sh 80'
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