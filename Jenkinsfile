pipeline {
     agent {
                        label "Windows_Node"
           }
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "Windows_Node"
                }
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "Windows_Node"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "Windows_Node"
                    }
                    steps {
						echo "Task1 on Master"
					}
                }
            }
        }
    }
}
