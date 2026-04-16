pipeline {
    agent any

    tools {
        maven 'Maven' 
        gradle 'Gradle'  // Ensure this matches the name configured in Jenkins
        jdk 'JDK'// Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Shukruth-Gowda/MyMavenToGradle.git'
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
