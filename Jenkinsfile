pipeline {
   agent {
    label 'ansible'
   }
    stages {
        stage('Prepare') {
            steps {
                sh "rm -rf vector-role"
                sh "git clone -b main https://github.com/northsilver/vector-role.git"
                sh "docker pull docker.io/pycontribs/centos:8"
                sh "docker pull docker.io/pycontribs/ubuntu:latest"
            }
        }
        stage('Test') {
            steps {
                dir('vector-role') {
                    sh "molecule test"
                }
            }
        }
    }
}