@Library('nik-shared-lib') _
pipeline {
    agent any
    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
    //     choice choices: ['create', 'delete'], description: 'Choose Create/Destroy', name: 'action'
    }
    stages{
        stage('Git Checkout'){
            when { expression { params.action == 'create'} }
            steps {
           git branch: 'main', url: 'https://github.com/nikhilve99/mocha_hello_world.git'
            }
        }
        stage('unit test case'){
            when { expression{ params.action == 'create'} }
            steps {
                script{
                    npmTest()
                }                
            }
        }
    }
}
