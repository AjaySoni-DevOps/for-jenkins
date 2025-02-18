pipeline {
    agent {
        label 'machine1'  // Specify your agent here
    }
    stages {
        stage('Running stage 1 printing') {
            steps {
                echo 'Hello World'
            }
        }

    
        
        stage('Building') {
            steps {
                sh ' echo ${BUILD_NUMBER}'
                // Build the Docker image
                sh 'docker build -t myimage-${BUILD_NUMBER} .'
                
                // Run the Docker container
                sh 'docker run -d -p 32533:80 --name my-container-${BUILD_NUMBER} myimage-${BUILD_NUMBER}'  // Added -d for detached mode
            }
        }
    }
}

