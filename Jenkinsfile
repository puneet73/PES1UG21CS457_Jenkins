pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Assuming you have a Jenkinsfile in your source code repository
                    checkout scm

                    // Compile the .cpp file using a shell script
                    sh 'g++ main/hello.cpp -o output'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run the compiled binary
                    sh './output'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
