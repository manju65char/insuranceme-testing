pipeline {
    agent any 

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven-3.8.7"
    }

    environment {    
        DOCKERHUB_CREDENTIALS = credentials('dockerloginid')
    } 
    
    stages {
        stage('SCM Checkout') {
            steps {
                // Get some code from a GitHub repository
                git url: 'https://github.com/manju65char/insuranceme-testing.git'
            }
        }
        
        stage('executing the test case') {
            steps {
                sh 'sudo java -jar insuremeseleniumtest.jar'
            }
        }
    }
}

