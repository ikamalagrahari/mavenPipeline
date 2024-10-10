pipeline {
    agent any
    stages {
        stage('clone repo & clean') {
            steps {
                bat 'if exist "mavenPipeline" rmdir /S /Q "mavenPipeline"'  // Check if directory exists before deleting
                bat "git clone https://github.com/ikamalagrahari/mavenPipeline.git"
                bat "mvn clean -f mavenPipeline"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test -f mavenPipeline"
            }
        }
        stage('Deploy') {
            steps {
                bat "mvn package -f mavenPipeline"
            }
        }
    }
}
