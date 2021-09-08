pipeline {
    agent any

    stages {
        stage('Stg1') {
            steps {
                	echo "Step 1"
            }
        }
        stage('Stg2') {
            parallel
            {
            	stage('2.1')
                {
            
            		steps {
                		echo "Paralell Step 1 in stg2"
            		}
                }
                stage('2.2')
                {
            
            		steps {
                		echo "Parallel Step 2 in stg2"
            		}
                }
           }
        }
    }
}