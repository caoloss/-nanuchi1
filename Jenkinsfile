pipeline {
    agent any
    tools{
        gradle 'Gradle'
        }
 stages {
    stage('Build') {
            steps {
                    sh './gradlew clean build --no-daemon'                                        
            }
        }
  stage('Docker Build and Tag') {
           steps {
                sh 'docker build -t shabnam790/internaldemo .' 
          }
        }
     
  stage('Publish image to Docker Hub') { 
            steps {
        withDockerRegistry([ credentialsId: "dockerhub", url: "" ]) {
          sh  'docker push shabnam790/internaldemo'
        }
          }
        }
 }
}
