pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    timeout(time: 10, unit: 'MINUTES') {
                        // Pulling the changes of the repo
                        sh 'git pull https://gitlab.com/houafilyas/webapp.git master'
                        sh 'sudo docker-compose build'
                        // Build the Docker images of the application
                    }        
                }
            }
        }   
    } 
}
