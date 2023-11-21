@Library('my-shared-library') _

pipeline{
    agent any
    parameters {
        choice(name: 'action', choices: 'create\ndelete', description: 'Chose create or destory')
    }
    stages{
        stage("Git Checkout"){
            when { expression {param.action == 'create'}}
            steps{
              gitCheckout(
                branch: 'master',
                url: 'https://github.com/sachin064/jenkin-javaapplication.git'
              )
            }
        }
        stage('Unit Test Maven')
        {
        when { expression {param.action == 'create'}}
            steps{
                mvnTest()
            }
        }
        stage('Intigation test maven'){
        when { expression {param.action == 'create'}}
            steps{
                mnvIntigrationTests()
            }
        }
        stage('Static Code analysis: sonarcube'){
        when { expression {param.action == 'create'}}
            steps{
                staticCodeAnalysis()
            }
        }
    }

}
