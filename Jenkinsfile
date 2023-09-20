pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                sh 'sudo -S cp /var/lib/jenkins/.m2/repository/com/example/HelloWorldProject/1.0.0/HelloWorldProject-1.0.0.jar  /var/lib/tomcat9/webapps'
            }
        }
        
        stage('Restart Tomcat') {
            steps {
                // Restart Tomcat
                sh '/path/to/tomcat/bin/shutdown.sh'
                sh '/path/to/tomcat/bin/startup.sh'
            }
        }
    }
    
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed! Take necessary actions.'
        }
    }
}
