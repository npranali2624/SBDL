pipeline {
    agent any

    stages {
        stage('Build') {
            steps {

                bat '"C:\\Users\\DELL\\AppData\\Local\\Programs\\Python\\Python311\\Scripts\\pip.exe" install -r requirements.txt'

s
            }
        }
        stage('Test') {
            steps {
                bat 'pytest'
            }
        }
        stage('Package') {
            when {
                anyOf { branch "master"; branch "release" }
            }
            steps {
                bat 'powershell Compress-Archive -Path lib -DestinationPath sbdl.zip -Force'
            }
        }
    }
}
