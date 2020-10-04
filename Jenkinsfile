pipeline {
	agent {
	    docker {
	      image  'ghcr.io/ionic-team/ionic-cli:6.11.10'
          args '-v $PWD:/usr/src/app/ -u 0:0'
	    }
	}
    stages {

       stage('NPM Setup') {
          steps {
	     sh 'ls -l'
             sh 'ionic --version'
	     sh 'ionic info'
         }
       }

       stage('Ionic Info') {
	       steps {
	           sh 'ionic info'
	       }
       }

    }
}
