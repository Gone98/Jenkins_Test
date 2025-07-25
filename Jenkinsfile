pipeline {
    agent { label 'my_wins'} 
    stages {  
        stage('Authenticate to GCP') {
            steps {
                withCredentials([file(credentialsId: 'gcp-instance-gp', variable: 'GCSKEY')]) {
                    // Authenticate to GCP
                    bat 'gcloud auth activate-service-account --key-file="%GCSKEY%"'
                    // Show current authenticated account
                    bat 'gcloud auth list'
                }
            }
        }
        stage('Remove Instance from Instance Group') {
            steps {
                // Replace the placeholders with your actual values
                bat 'gcloud compute instance-groups managed remove-instances lbtest-ap1  --instances=lbtest-ap1  --zone=asia-northeast1-c'
            }
        }
    }
}