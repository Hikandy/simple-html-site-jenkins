pipeline {
    agent { 
        dockerfile {
            filename 'Dockerfile'
            args '-p 80:80'
        }
    }
    stages {
        stage('build') {
            steps {
                sh 'curl localhost:80'
            }
        }
    }
}