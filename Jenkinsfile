pipeline  {
    agent { label 'ubuntu' }
    stages {
        stage('Build & UnitTest') {
            steps {
                sh "docker build -t accountownerapp:B${BUILD_NUMBER} -f Dockerfile ."
                sh "docker build -t accountownerapp:test-B${BUILD_NUMBER} -f Dockerfile.Integration ."
            }
        }
        stage('Integration Test') {
            steps {
                sh "docker-compose up --force-recreate --abort-on-container-exit"
                sh "docker-compose down -v"
            }
        }
    }  
}

