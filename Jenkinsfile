pipeline  {
    agent { label 'ubuntu' }
    stages {
        stage('Build & UnitTest') {
            steps {
                sh "docker build -t accountownerapp:B${BUILD_NUMBER} . "
            }
        }
        stage('Integration Test') {
            steps {
                sh "docker run -t accountownerapp:B${BUILD_NUMBER} "
            }
        }
    }  
}

