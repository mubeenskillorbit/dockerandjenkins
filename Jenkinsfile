pipeline  {
    agent { label 'ubuntu' }
    stages {
        stage('Build & UnitTest') {
            steps {
                docker build -t accountownerapp .
            }
        }
        stage('Integration Test') {
            steps {
                docker run -t accountownerapp
            }
        }
    }  
}

