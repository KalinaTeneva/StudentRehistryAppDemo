 pipeline{
    agent any

    stages{
        stage('Chekout'){
           
        }
        stage('Install dependies'){
            steps{
                script{
                    bat 'npm install'
                }
            }
        }
        stage('Start application and run tests'){
            steps{
                script{
                    bat 'start /b npm start'
                }
            }
        }
        stage("run tests"){
            steps{
                script{
                    bat 'npm test'
                }
            }
        }
        
    }
 }   