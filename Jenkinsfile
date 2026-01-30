pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID     = "credentials('aws-creds').accessKey"
        AWS_SECRET_ACCESS_KEY = "credentials('aws-creds').secretKey"
        AWS_REGION            = "ap-south-1"
        TF_VAR_bucket_name    = "terraform-pipeline-sanoj-12345"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kvsanojkv/terraform-jenkins-lab.git'
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }

        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}

