pipeline {
    agent any
    stages {  
        stage('Test ssh connection') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: "test_id", keyFileVariable: 'keyfile')]) {                 
                sh '''
		ssh -T -i $keyfile ubuntu@ec2-18-222-202-164.us-east-2.compute.amazonaws.com
		cd /home/ubuntu/django-project/
		git checkout master
		git pull
		chmod +x update.sh
		sudo systemctl stop django-project
		./update.sh
		sudo systemctl start django-project
		
		'''            
               }
            }
        }
    }
}

