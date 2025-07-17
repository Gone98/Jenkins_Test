pipeline {
 agent any  
parameters {  
    choice(name: 'containers', choices: ['mytomcat'], description: 'SSH server')  
}  
stages {  
    stage('Test') {  
        steps([$class: 'BapSshPromotionPublisherPlugin']) {
                script {
                    // SERVERS_LISTをカンマで分割してサーバーリストの配列を作成する
                    env.serverList =  params.containers
                    
							sshPublssisher(
								publishers: [
									sshPublisherDesc(
										configName: "${env.serverList}",
										transfers: [
											sshTransfer(
												execCommand: "cat test1.txt",
												remoteDirectory: "rkuwartest_jenkins", 
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