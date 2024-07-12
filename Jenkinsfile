pipeline {
    agent {
        label "docker"
    }
    stages {
        stage ('code'){
            steps {
                git url: "https://github.com/Explorer-Space/Flask_App.git", branch: "main"
                echo "Git Repository Cloned Successfully"
                sh "git --version"
                sh "docker --version"
            }
        }
        stage('Build and Test'){
            steps {
                sh 'docker build -t docker-host:5000/flask-app:public .'
                echo "Docker Image Built Successfully"
            }
        }
        stage('Push'){
            steps {
                sh 'docker login -u dock_user -p dock_password docker-host:5000'
                echo "logged in successfully"
                sh 'docker push docker-host:5000/flask-app:public'
            }
        }
        
        
    }
}
