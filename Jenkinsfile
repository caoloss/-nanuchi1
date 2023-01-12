pipeline {
    agent any
 stages {
  stage('Docker Build and Tag') {
           steps {
                sh 'docker build -t shabnam790/internaldemo .' 
                  sh 'docker tag shabnam790/internaldemo:latest' 
          }
        }
  stage('Publish image to Docker Hub') { 
            steps {
        withDockerRegistry([ credentialsId: "dockerhub", url: "" ]) {
          sh  'docker push shabnam790/internaldemo:latest'
        }
          }
        }
 }
}
