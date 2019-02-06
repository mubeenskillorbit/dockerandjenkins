pipeline  {
    agent { label 'ubuntu' }
    stages {
        stage('Build & UnitTest') {
            steps {
                docker build -t accountownerapp:B${BUILD_NUMBER} .
            }
        }
        stage('Integration Test') {
            steps {
                docker run -t accountownerapp:B${BUILD_NUMBER}
            }
        }
    }  
}

