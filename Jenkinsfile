pipeline {
    agent any
    stages {  
        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: "$test_id", variable: 'ID')]) {                 
                env
                
               }
            }
        }
    }
}
