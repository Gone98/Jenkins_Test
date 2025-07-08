pipeline {
    agent {
        label 'my_wins'
    }
    stages {
        stage('Example') {
            steps {
                script{
                    bat 'docker run -d -t maven:3.9.3-eclipse-temurin-17'
                }
            }
        }
    }
}