pipeline {
    agent any
    stages{
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/bike.txt'
                sh 'echo "Fahrradrahmen montieren" >> build/bike.txt'
            }
        }
        stage('Test') {
            script {
                def filePath = 'build/bike.txt'
                if (fileExists(filePath)) {
                    echo 'Die Datei existiert ${filePath}'
            }
            }
        }
    }
}