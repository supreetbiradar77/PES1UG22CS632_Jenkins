pipeline {
    agent any  

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o hello_exec hello.cpp'  // Compile C++ file
                }
                build 'YOUR_SRN-1'  // Trigger first job
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './hello_exec'  // Run the compiled program
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed!'
        }
    }
}
