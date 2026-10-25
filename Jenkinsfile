pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'docker build -t college-web-image .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker rm -f college-web-container 2>NUL || exit /b 0'
                bat 'docker run -d -p 8081:80 --name college-web-container college-web-image'
            }
        }
    }
}
