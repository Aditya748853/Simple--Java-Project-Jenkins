pipeline {
    agent any

    tools {
        jdk 'java'   // Ensure this matches the JDK configured in Jenkins
        maven 'maven' // Ensure this matches the Maven configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/yourusername/SimpleJavaProject.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Run') {
            steps {
                sh 'java -cp target/simple-java-project-1.0-SNAPSHOT.jar com.example.HelloWorld'
            }
        }
    }

    post {
        success {
            echo 'Build and execution successful!'
        }
        failure {
            echo 'Build or execution failed.'
        }
    }
}
