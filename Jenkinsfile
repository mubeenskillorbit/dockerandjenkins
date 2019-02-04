
node('ubuntu') {
    stages {
        stage('Build & UnitTest') {
            step {
                sh "docker build -t accountownerapp:B${BUILD_NUMBER} -f Dockerfile ."
                sh "docker build -t accountownerapp:test-B${BUILD_NUMBER} -f Dockerfile.Integration ."
            }
        }
        stage('Integration Test') {
            step {
                sh "docker-compose up --force-recreate --abort-on-container-exit"
                sh "docker-compose down -v"
            }
        }
    }  
}
