 pipeline{
    agent any

    stages{
        stage('Chekout'){
            steps{
                git brach: 'main', url: 'https://github.com/KalinaTeneva/StudentRehistryAppDemo'
            }

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
                    sh 'npm start'
                    sh 'wait-on http://localhost:8090'
                    sh 'npm test'
                }
            }
        }
        
    }
    post{
            always{
                echo "CI pipeline completed"
            }
        }
}