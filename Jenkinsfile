pipeline {
    agent any
    stages {  
        stage('Test ssh connection') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: "test_id", keyFileVariable: 'keyfile')]) {                 
                sh '''
		ssh -i ${keyfile} admin@ec2-18-222-202-164.us-east-2.compute.amazonaws.com
		env
		uname -a
		'''            
               }
            }
        }
    }
}

