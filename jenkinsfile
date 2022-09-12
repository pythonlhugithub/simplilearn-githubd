pipeline {
    agent {
        label 'WindowNode'
    }
    stages {
        
        stage('mamy test'){
            parallel{
                stage ('test on window'){
            agent {
                label 'WindowNode'
            }
            steps {
                echo 'window agent is running'
            }
                }
                stage('test on linux'){
            agent {
                label 'WindowNode'
            }
            steps {
                echo 'linux agent is running'
            }
                }
            }
        }
        
       
        
        stage('check-out') 
        {
            steps {
                git 'https://github.com/pythonlhugithub/simplilearn-githubd.git'
             
            }
            
        }

 stage('build'){
    steps{
        echo 'build-git-checkout'
        bat 'Build.bat'
     }
    }
    
      stage('unit test'){
    steps{
        echo 'unittest-git-checkout'
        bat 'Unit.bat'
       } 
    }
      stage('quality gate'){
    steps{
        echo 'quality-git-checkout'
        bat 'Quality.bat'
       } 
    }
    
       stage('deploy'){
    steps{
        echo 'deploy-git-checkout'
       bat 'Deploy.bat'
    }
    }
    }

post {
                
                success {
                 echo "success"
                }
            }
}


 
