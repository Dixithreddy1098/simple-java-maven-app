
pipeline {
    agent any
    stages {
        stage ('BUILD_STAGE') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    
        stage ('TESTING_STAGE') {

            steps {
                sh 'mvn test'
        
            }
        }
        stage ('Archivetheatrficats') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
                Junit 'target/surefire-reports/*.xml'
            }
        }
            
        
    }
}
