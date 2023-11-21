@Library('my-shared-library') _

pipeline{
    agent any
    parameters {
        choice(name: 'action', choices: 'create\ndelete', description: 'Chose create or destory')
    }
    stages{
        stage("Git Checkout"){
            when { expression {params.action == 'create'}}
            steps{
              gitCheckout(
                branch: 'master',
                url: 'https://github.com/sachin064/jenkin-javaapplication.git'
              )
            }
        }
        stage('Unit Test Maven')
        {
        when { expression {params.action == 'create'}}
            steps{
                mvnTest()
            }
        }
        stage('Intigation test maven'){
        when { expression {params.action == 'create'}}
            steps{
                mnvIntigrationTests()
            }
        }
        stage('Static Code analysis: sonarcube'){
        when { expression {params.action == 'create'}}
            steps{
                staticCodeAnalysis()
            }
        }
    }

}
