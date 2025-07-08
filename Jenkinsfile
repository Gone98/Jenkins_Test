pipeline {
    agent {
        docker {
            image 'maven:3.9.3-eclipse-temurin-17'
            label 'my_wins'
            args  '-v Test First Pipeline:/tmp'
        }
    }
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
    }
}