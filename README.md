# JenkinsProject

 * * * * *
 
node{
stage('checkout')
git 'https://github.com/DigitConsultancy/JenkinsProject.git'
bat 'mvn clean package'
archiveArtifacts 'target/*.jar'
}
