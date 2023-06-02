@Library('nik-shared-lib') _
pipeline {
    agent any
    stages{
        stage('Git Checkout'){
            steps {
           git branch: 'main', url: 'https://github.com/nikhilve99/mocha_hello_world.git'
            }
        }
        stage('unit test case'){
            steps {
                script{
                    npmTest()
                }                
            }
        }
    }
}
