pipeline {
    agent any 
    stages {
        stage('Stage-1 : Clean') { 
            steps {
                sh 'mvn clean'
            }
        }
        stage('Stage-2 : Validate') { 
            steps {
                sh 'mvn validate'
            }
        }
  
    }
}
