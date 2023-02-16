pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar'
            }
        }
    stage ('Unit Test')
       {
            steps {
              sh "mvn test"
            }
            post {
                always {
                    sh 'mvn site'
                  // junits 'target/surefire-reports/*.xml'
                  //  jacoco execPattern: 'target/jacoco.exec'
               } 
            }
        }
    }
}