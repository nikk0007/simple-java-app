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
                script {
          def testOutput = sh(returnStdout: true, script: 'mvn test')
          echo "Test output:\n${testOutput}"
        }
            }
        }
    }
}
