pipeline {
    agent none

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'maven:3.9.0'
                    args '-v /root/.m2:/root/.m2'
                }
            }
            steps {
                echo 'Running Build stage'
                sh 'mkdir qwerty'
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            agent {
                docker {
                    image 'maven:3.9.0'
                    args '-v /root/.m2:/root/.m2'
                }
            }
            steps {
                echo 'Running Test stage'
                sh 'mvn test'
            }
        }
        stage('Deliver') {
            agent {
                docker {
                    image 'maven:3.9.0'
                    args '-v /root/.m2:/root/.m2'
                }
            }
            steps {
                echo 'Running Deliver stage'
                sh './scripts/deliver.sh'
            }
        }
    }

    post {
        always {
            echo 'posttt'
            junit 'target/surefire-reports/*.xml'
        }
    }
}
