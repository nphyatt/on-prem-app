pipeline {
    agent none
    stages {

       stage('NPM Setup') {
	  agent { docker { image  'ghcr.io/ionic-team/ionic-cli:6.11.10' } }
          steps {
             sh 'ionic --version'
	     sh 'ionic info'
         }
       }

       stage('Ionic Info') {
	       agent { docker { image  'ghcr.io/ionic-team/ionic-cli:6.11.10' } }

	       steps {
	           sh 'ionic info'
	       }
       }

    }
}
