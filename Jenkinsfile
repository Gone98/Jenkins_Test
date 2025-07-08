pipeline {
    agent {
        docker {
            image 'maven:3.9.3-eclipse-temurin-17'
            label 'my_wins'
            args  '-v C:\Test Env\Jenkins_Agent\workspace:/tmp'
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