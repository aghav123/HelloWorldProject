pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'checkout scm'
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
    }
}
    
