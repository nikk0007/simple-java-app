pipeline {
    agent {
        docker {
            image 'maven:3.9.0'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'echo Test Stage'
                sh 'mvn test'
            }
        }
        stage('Deliver') {
            steps {
                sh 'echo Stage Deliver'
                sh './scripts/deliver.sh'
            }
        }
        post {
                always {
                    sh 'echo posttt'
                    junit 'target/surefire-reports/*.xml'
                }
            }
    }
}
