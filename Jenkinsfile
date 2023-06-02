pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    timeout(time: 10, unit: 'MINUTES') {
                        sh 'sudo su'
                        sh 'cd /home/webapp'
                        // Pulling the changes of the repo
                        sh 'git pull https://gitlab.com/houafilyas/webapp.git master'
                        sh 'sudo docker-compose build'
                        // Build the Docker images of the application
                    }        
                }
            }
        }
        
        // Add more stages here if needed
        
        stage('Deploy') {
            steps {
                script {
                    // Start the Docker containers
                    sh 'docker-compose up -d'
                }
            }
        }
    }
    
    post {
        always {
            // Clean up Docker containers and images
            cleanDocker()
        }
    }
}

def cleanDocker() {
    script {
        // Stop and remove the Docker containers
        sh 'docker-compose down'
        
        // Remove the Docker images
        sh 'docker-compose rm -f'
    }
}
