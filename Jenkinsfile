pipeline {
  agent any

  tools {
    nodejs "nodejs"

  }

  stages {
    stage ('Build') {
      steps {
        sh 'npm install'

      }

    }

    stage('Build Docker Image') {
      steps {
        script {
          docker.build("username/imagename:tag")
        }
      }
    }

    stage('Push Docker Image') {
      steps {
        script {
          docker.withRegistry('https://index.docker.io/v1/', 'ba157297-582b-4d33-8f91-5b52bc1ca372') {
            dockerImage.push()
          }
        }
      }
    }

  }

}
