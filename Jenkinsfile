pipeline {
    agent any
    environment {
        TF_VAR_region = 'us-east-1'
        AWS_ACCESS_KEY_ID = credentials('aws-credentials')
        AWS_SECRET_ACCESS_KEY = credentials('aws-credentials')
    }
    stages {
        stage('Checkout') {
            steps {
                git branch:'main', url:'https://github.com/VasuKotha2/Terraform-Project.git'
            }
        }
        stage('Terraform version check'){
            steps{
                sh 'terraform --version'
            }
        }
        stage('Terraform initialization'){
            steps{
                sh 'terraform init'
            }
        }
        stage('terraform validate'){
            steps{
                sh 'terraform validate'
            }
        }
        stage('plan'){
            steps{
                sh 'terraform plan'
            }
        }
        stage('terraform apply'){
            steps{
                sh 'terraform apply --auto-approve'
            }
        }
    }
}

