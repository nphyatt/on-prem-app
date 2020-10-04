pipeline {

    agent any

    environment {
        PATH='/home/bitnami/.nvm/versions/node/v12.18.4/bin:/opt/bitnami/apache/bin:/opt/bitnami/apache2/bin:/opt/bitnami/common/bin:/opt/bitnami/git/bin:/opt/bitnami/gonit/bin:/opt/bitnami/java/bin:/opt/bitnami/java/jre/bin:/opt/bitnami/nami/bin:/opt/bitnami/apache/bin:/opt/bitnami/apache2/bin:/opt/bitnami/common/bin:/opt/bitnami/git/bin:/opt/bitnami/gonit/bin:/opt/bitnami/java/bin:/opt/bitnami/java/jre/bin:/opt/bitnami/nami/bin:/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games'
	NVM_BIN='/home/bitnami/.nvm/versions/node/v12.18.4/bin'
    }

    stages {

       stage('NPM Setup') {
          steps {
             sh 'npm install'
         }
       }

       stage('IOS Build') {
          steps {
             sh 'ionic cordova build ios --release'
             
          }
       }

       stage('Android Build') {
          steps {
               sh 'ionic cordova build android --release'
               
          }
       }

       stage('APK Sign') {
          steps {
            // sh 'jarsigner -storepass your_password -keystore keys/yourkey.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk nameApp'
              echo "Android"
          }
       }



      stage('Stage Web Build') {
          steps {
              sh 'npm run build --prod'
          }
       }

         stage('Publish Firebase Web') {
          steps {
              //sh 'firebase deploy --token "YourTokenKey"'
              echo 'Firebase Deploy'
          }
       }

        stage('Publish iOS') {
          steps {   
              echo "Publish iOS"
          }
       }

        stage('Publish Android') {
          steps {
              echo "Publish Android"
          }
       }


}
}
