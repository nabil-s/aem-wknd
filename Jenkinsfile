node {
    docker.image('maven:3-alpine').inside('-v $HOME/.m2:/root/.m2 --network container:sonarqube') {
        stage('Build') {
            echo 'Building...'
            sh 'mvn --version'
        }
        stage('Scan') {
            echo 'Scanning...'
            sh 'mvn -X -DskipTests -f pom.xml clean install sonar:sonar'
        }
        stage('Test') {
            echo 'Testing...'
        }
        stage('Deploy') {
            echo 'Deploying...'
        }
    }
}