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
                println 'echo build'
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
