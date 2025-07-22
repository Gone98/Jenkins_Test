pipeline {
 agent any  
parameters {  
    choice(name: 'containers', choices: ['mytomcat','testjenkins'], description: 'SSH server')  
}  
stages {  
    stage('Test') {  
        steps([$class: 'BapSshPromotionPublisherPlugin']) {
                script {
                    // SERVERS_LISTをカンマで分割してサーバーリストの配列を作成する
                    env.serverList =  params.containers
                    
							sshPublisher(
								publishers: [
									sshPublisherDesc(
										configName: "${env.serverList}",
										transfers: [
											sshTransfer(
												execCommand: "echo \$? > result.txt",
												remoteDirectory: "test_jenkins", 
												sourceFiles: 'test1.txt'
											)
										], 
									)
								]
							)
                }    
        }
    }
}
}