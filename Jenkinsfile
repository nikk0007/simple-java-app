pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Run Maven build
                sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests
                sh 'mvn test'
            }
        }
        
        stage('Deploy') {
            steps {
                // Perform deployment steps if required
                // For example, deploying to a remote server
                //sh 'mvn deploy'
                echo 'DEPLOY STAGE'
            }
        }

        stage('Deliver') {
            steps {
                sh 'echo "Stage Deliver"'
                sh 'sh scripts/deliver.sh'
            }
        }
     post {
        always {
            // Cleanup steps or actions that should be performed regardless of the stage outcomes
            
            // For example, cleaning up temporary files
            //sh 'rm -rf target'
            echo 'ALWAYS'
        }
        
        success {
            // Actions to be performed only if the pipeline succeeds
            
            // For example, sending a notification
            echo 'Pipeline succeeded! Sending notifications...'
        }
    failure {
            // Actions to be performed only if the pipeline fails
            
            // For example, sending an email or Slack notification
            echo 'Pipeline failed! Sending failure notifications...'
        }
    }
        
    }
}
