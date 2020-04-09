
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
        post {
            always {
                 archive "target/*.jar"
                 junit 'target/surefire-reports/*.xml'
            }
        }
            
        
    }
}
