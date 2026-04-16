pipeline {
    agent any

    tools {
        maven 'maven' 
        gradle 'gradle'  // Ensure this matches the name configured in Jenkins
        jdk 'java'// Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/prithvicatalog/maven_to_gradle.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('migrate') {
            steps {
                sh 'gradle init --type pom'  // Run unit tests
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
