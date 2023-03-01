pipeline {
  agent any
 
  stages {
      stage('Install') {
      steps {
        bat 'npm install'
      }
    }
     stage('Coding Convention') {
      steps {
        bat 'npx eslint src'
      }
    }
      stage('Test') {
      steps {
        bat 'npm test'
      }
    }
    stage('Build') {
      steps {
        bat 'npm run build'
      }
    }
    stage("Delete"){
      steps {
        folderOperations([folderDeleteOperation(
        excludes: '',
        folderPath: "C:\\xampp\\htdocs"
        )])
      }
    }
    stage("Copy"){
      steps {
        folderOperations([folderCopyOperation(
        sourceFolderPath : "./build", 
        excludes: '',
        destinationFolderPath: "C:\\xampp\\htdocs"
        )])
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