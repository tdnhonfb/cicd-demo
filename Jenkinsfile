pipeline {
  agent any
 
  stages {
      stage('Install') {
      steps {
        bat 'npm install'
      }
    }
    stage('Test') {
      steps {
        bat ' npm test -- App.test.js'
      }
    }
    stage('Build') {
      steps {
        bat 'npm run build'
      }
    }
    // stage('Push to Heroku registry') {
    //   steps {
    //     sh '''
    //       docker tag $IMAGE_NAME:$IMAGE_TAG registry.heroku.com/$APP_NAME/web
    //       docker push registry.heroku.com/$APP_NAME/web
    //     '''
    //   }
    // }
    // stage('Release the image') {
    //   steps {
    //     sh '''
    //       heroku container:release web --app=$APP_NAME
    //     '''
    //   }
    // }
  }
//   post {
//     always {
//       sh 'docker logout'
//     }
//   }
}