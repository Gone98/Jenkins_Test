pipeline {
 agent my_wins 
parameters {  
    choice(name: 'containers', choices: ['mytomcat','testjenkins'], description: 'SSH server')  
}  
stages {  
    stage('Authenticate to GCP') {
            steps {
                withCredentials([file(credentialsId: 'gcp-instance-gp', variable: 'GCSKEY')]) {
                    // Use the path stored in the GCSKEY environment variable
                    sh "gcloud auth activate-service-account --key-file=${GCSKEY}"

                }
            }
    }
}
}