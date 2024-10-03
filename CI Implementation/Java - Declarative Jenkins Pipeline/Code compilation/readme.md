


```
pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/OT-MICROSERVICES/salary-api.git'
            }
        }
        stage('Compile') {
            steps {
                script {
                    // Navigate to the root directory where the pom.xml file is located
                    dir('/var/lib/jenkins/workspace/salary-api/code-compilation') {
                        // List files for debugging
                        sh 'ls -R'
                    }
                    // Assuming the pom.xml is at the root of the repository
                    sh 'mvn compile' 
                    
                    }
            }
        }
    }
    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
```
