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
                sh 'zip -r Catalogu-1.zip ./* --exclude=.git --exclude=.zip'  
            }   
        }

        stage('Publish Artifact') { 
            steps {
                nexusArtifactUploader(
                    nexusVersion: 'nexus3',
                    protocol: 'http',
                    nexusUrl: '54.198.138.85:8081/',
                    groupId: 'com.roboshop',
                    version: '1.0.1',
                    repository: 'catalogue',
                    credentialsId: 'nexus-auth',
                    artifacts: [
                        [artifactId: 'catalogue',
                        classifier: '',
                        file: 'Catalogu-1.zip',
                        type: 'zip']
                    ]
                )
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
