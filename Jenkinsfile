 pipeline{
    agent any
    environment{
        NODE_VERSION = '20.x'
    }

    tools{
        nodejs"${NODE_VERSION}"
    }

    stages{
        stage('Chekout'){
            steps{
                git brach: 'main', url: 'https://github.com/KalinaTeneva/StudentRehistryAppDemo'
            }

        }
        stage('Install dependies'){
            steps{
                script{
                    if(isUnix()){
                        bat 'npm install'
                    }else{
                        sh 'npm install'
                    }
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