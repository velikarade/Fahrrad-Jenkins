pipeline {
    agent any
    stages{
        stage('Build') {
            script {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/bike.txt'
                sh 'echo "Fahrradrahmen montieren" >> build/bike.txt'
            }
        }
    }
}