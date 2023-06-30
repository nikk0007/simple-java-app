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
                sh './scripts/deliver.sh'
            }
        }
        post {
                always {
                    echo 'posttt'
                    junit 'target/surefire-reports/*.xml'
                }
            }

        
    }
}
