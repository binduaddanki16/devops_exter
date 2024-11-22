pipeline {
    agent any  // This allows Jenkins to run the pipeline on any available agent

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your GitHub repository
                git url: 'https://github.com/binduaddanki16/devops_exter.git', branch: 'main'
            }
        }
        
        stage('Compile Java File') {
            steps {
                // Compile the Calci.java file using javac
                sh 'javac calci.java'
            }
        }

        stage('Run Java Program') {
            steps {
                // Run the Java program
                sh 'java calci'  // This assumes your main class is Calci.java
            }
        }
        
        stage('Archive Output') {
            steps {
                // Archive the compiled .class file so you can download it if needed
                archiveArtifacts '**/*.class'
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
