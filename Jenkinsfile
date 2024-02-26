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
        stage('Test'){
            steps {
                script {
                    def filePath = 'build/bike.txt'
                    if (fileExists(filePath)) {
                        echo "Die Datei exitiert ${filePath}"
                        def fileContent = readFile(filePath).trim()
                        def expectedContent = 'Fahrradrahmen montieren'
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
}