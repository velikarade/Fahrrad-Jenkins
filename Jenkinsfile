pipeline {
    agent any
    stages{
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/bike.txt'
                sh 'echo "Fahrradrahmen montieren\nRäder montieren\nPadele montieren\nLackierung" >> build/bike.txt'
            }
        }
        stage('Test'){
            steps {
                script {
                    def filePath = 'build/bike.txt'
                    if (fileExists(filePath)) {
                        echo "Die Datei exitiert ${filePath}"
                        def fileContent = readFile(filePath).trim()
                        def expectedContent = 'Fahrradrahmen montieren\nRäder montieren\nPadele montieren\nLackierung'
                        if (fileContent == expectedContent) {
                            echo "Der Inhalt stimmt überein"
                        }
                        else {
                            error "Der Inhalt stimmt nicht überein"
                        }
                    }
                    else {
                        error "Die Datei exiriert nicht"
                    }
                }
            }
        }
    }
    post {
        always {
            archiveArtifacts 'build/bike.txt'
            echo 'Die Datei ist archiviert'
        }
    }
}