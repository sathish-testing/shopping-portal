pipeline{

    agent any

// uncomment the following lines by removing /* and */ to enable
    tools{
       nodejs ‘nodejs’ 
    }    

    stages{
        stage(‘com’pile){
            steps{
                echo 'this is the first job'
                sh ’npm install’
                sleep 4
            }
        }
        stage(‘test’){
            steps{
                echo 'this is the second job'
                sh ‘npm test’
                sleep 9
            }
        }
        stage(‘Package’){
            steps{
                echo 'this is the third job'
                sh ’npm run package’
                sleep 7
            }
        }
    }
    
    post{
        always{
            echo 'this pipeline has completed...'
        }
        
    }
    
}

