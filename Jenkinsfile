pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Pull the latest Docker images
                    sh 'docker-compose up'
                    
                    // Build the Docker containers
                    //sh 'docker-compose build'
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

