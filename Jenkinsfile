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
        stage('build') { 
            steps {
                sh 'ls -ltr'  
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
            deleteDir()
        }
    }

}
