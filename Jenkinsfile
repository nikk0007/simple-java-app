pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "build tage"'
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Test Stage"'
                sh 'mvn test'
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
