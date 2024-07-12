pipeline {
    agent {
        label "docker"
    }
    stages {
        stage ('code'){
            steps {
                git url: "http://git.kodekloud.com:3000/max/Flask-App.git", branch: "master"
                echo "Git Repository Cloned Successfully"
                sh "git --version"
                sh "docker --version"
            }
        }
        stage('Build and Test'){
            steps {
                sh 'docker build -t flask-app-image .'
                echo "Docker Image Built Successfully"
            }
        }
        
        
    }
}
