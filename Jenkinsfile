pipeline {
    agent { label 'my_wins'} 
    stages {  
        stage('Authenticate to GCP') {
            steps {
                withCredentials([file(credentialsId: 'gcp-instance-gp', variable: 'GCSKEY')]) {
                    // Authenticate to GCP
                    bat "gcloud auth activate-service-account --key-file=%GCSKEY%"
                    // Show current authenticated account
                    bat "gcloud auth list"
                }
            }
        }
    }
}