pipeline {
    agent any
    environment {
        imageName = "chawitcode/hello-nginx"
    }
    stages{
        stage("Prepare"){
            steps{
                echo "Hello World!"
            }
        }
        stage("Check_version"){
            steps{
                sh "docker --version"
            }
        }        
        stage("Build Image"){
            steps{
                sh "docker build -t ${env.imageName} ."
                sh "docker tag  ${env.imageName} ${env.imageName}:1.${env.BUILD_NUMBER}"
            }
        }
        stage("push image") {
            sh "docker push ${env.imageName}"
        }
    }
}
