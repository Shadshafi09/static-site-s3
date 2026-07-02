pipeline {
    agent any

    stages {
        stage('cloning code') {
            steps {
               git branch: 'main', url: 'https://github.com/Shadshafi09/static-site-s3.git'
            }
        }
        stage('build image'){
            steps{
                sh 'docker build -t mydocproj .'
            }
        }
        stage('run image'){
            steps{
               sh '''
docker stop mydocproj || true
docker rm mydocproj || true
docker run -d --name mydocproj -p 3000:80 mydocproj
'''
            }
        }
    }
}
