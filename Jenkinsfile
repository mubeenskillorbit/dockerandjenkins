pipeline  {
    agent { label 'ubuntu' }
    stages {
        stage('Build & UnitTest') {
            steps {
                sh "docker build -t accountownerapp ."
            }
        }
        stage('Integration Test') {
            steps {
                sh "docker run -t accountownerapp"
            }
        }
    }  
}

