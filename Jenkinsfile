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
                Chekout scm
            }

        }
        stage('Install dependies'){
            steps{
                script{
                    if(isUnix()){
                        sh 'npm install'
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