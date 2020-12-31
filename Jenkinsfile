pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "master"
                }
        steps {
                echo "Hi I am in non parallel stage"              }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "New_node"
                    }
                    steps {
                        echo "Hi I am on new node"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "master"
                    }
                    steps {
						echo "Hi am running test on Master"
					}
                }
            }
        }
    }
}
