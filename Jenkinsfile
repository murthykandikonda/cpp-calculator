pipeline {
    agent any

    stages {

        stage('Prepare') {
            steps {
                echo 'Cleaning build directory'
                sh 'rm -rf build'
                sh 'mkdir build'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project with CMake'
                dir('build') {
                    sh 'cmake ..'
                    sh 'make'
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                dir('build') {
                    sh './calculator'
                }
            }
        }
    }
}
