pipeline {
   agent any
   stages {
 stage(‘codecheckout’) {
 steps {
 git 'https://github.com/Ashabbe/terraform.git'
 
 }
 }
 stage(‘Setpath’) {
 steps {
 script {
 def tfHome = tool name: ‘Terraform’
 env.PATH = '${tfHome}:${env.PATH}'
 }
 bat ‘terraform — version’
 
 
 }
 }
 
 stage(‘Provisioninfrastructure’) {
 
 steps {
 dir(‘dev’)
 {
 bat ‘terraform init’
 bat 'terraform plan -out=plan'
 // sh ‘terraform destroy -auto-approve’
 bat ‘terraform apply plan’
 }
 
 
 }
 }
 
 
 
 
}
