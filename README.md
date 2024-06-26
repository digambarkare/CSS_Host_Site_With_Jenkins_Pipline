```
pipeline {
    agent any
    stages {
        stage('Pull') {
            steps {
                git 'https://github.com/Shantanu20000/CSS_Host_Site_With_Jenkins_Pipline.git'
                echo 'Pull Successfully'
                sh 'ls'
            }
        }
        stage('Build Docker image') {
            steps {
                script {
                    sh '''docker build -t dockerimage .
                          docker run -itd -p 80:80 dockerimage'''
                    echo 'Build Successfully'
                }
            }
        }
    }
}
```
