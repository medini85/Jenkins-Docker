pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat '"C:\Users\parab\AppData\Local\Programs\DockerDesktop\resources\bin\docker.exe" build -t college-web-image .'
            }
        }

        stage('Deploy') {
            steps {
                bat '"C:\Users\parab\AppData\Local\Programs\DockerDesktop\resources\bin\docker.exe" rm -f college-web-container 2>NUL || exit /b 0'
                bat '"C:\Users\parab\AppData\Local\Programs\DockerDesktop\resources\bin\docker.exe" run -d -p 8081:80 --name college-web-container college-web-image'
            }
        }
    }
}
