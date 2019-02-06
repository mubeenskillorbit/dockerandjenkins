pipeline  {
    agent { label 'ubuntu' }
    stages {
        stage('Build & UnitTest') {
            steps {
                sh "docker build -t accountownerapp:B${BUILD_NUMBER} -f Dockerfile ."
            }
        }
        stage('Integration Test') {
            steps {
                sh "docker run -t accountownerapp:B${BUILD_NUMBER}"
            }
        }
    }  
}

