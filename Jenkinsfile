pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                        sh 'pwd'
                    // Cloning the repo
                        sh 'git clone https://gitlab.com/houafilyas/webapp.git application'
                    dir('webapp') {
                        sh 'docker-compose up'
                        // Build the Docker containers
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
