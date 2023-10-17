pipeline {
    agent { node { label 'AGENT-1' } } 
    stages {
        stage('Install dependencies') { 
            steps {
                sh 'npm install'
            }
        }
        stage('unit test') { 
            steps {
                echo "unit testing is done here..abcd. s"
            }
        }
        // // sonar-scanner command expert sonar-project.properties should be available
        // stage('Sonar Scan') { 
        //     steps {
        //         sh 'ls -ltr' 
        //         sh 'sonar-scanner'   
        //     }   
        // }
        stage('Build') { 
            steps {
                sh 'ls -ltr'
                sh 'zip -r ./* --exclude=.git '  
            }   
        }


        stage('Deploy') { 
            steps {
                echo "Deployment"   
            }   
        }
    }
    
    post{
        always{
            echo 'Cleaning up workspace'
            // deleteDir()
        }
    }

}
