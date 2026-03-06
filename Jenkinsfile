pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                echo "Preparing build directory..."
                sh 'mkdir -p build'
            }
        }
        stage('Build') {
            steps {
                echo "Building project with CMake..."
                dir('build') {
                    sh 'cmake ..'
                    sh 'make'
                }
            }
        }
        stage('Test') {
            steps {
                echo "Running calculator program..."
                dir('build') {
                    sh './calculator'
                }
            }
        }
    }
}
