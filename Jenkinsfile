@Library('my-shared-library') _

pipeline{
    agent any
    stages{
        stage("Git Checkout"){
            steps{
              gitCheckout(
                branch: 'master',
                url: 'https://github.com/sachin064/jenkin-javaapplication.git'
              )
            }
        }
        stage('Unit Test Maven'){
            steps{
                mvnTest()
            }
        }
        stage('Intigation test maven'){
            steps{
                mnvIntigrationTests()
            }
        }
    }

}
