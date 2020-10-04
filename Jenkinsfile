pipeline {

    agent none

    /* environment {
        PATH='/home/bitnami/.nvm/versions/node/v12.18.4/bin:/opt/bitnami/apache/bin:/opt/bitnami/apache2/bin:/opt/bitnami/common/bin:/opt/bitnami/git/bin:/opt/bitnami/gonit/bin:/opt/bitnami/java/bin:/opt/bitnami/java/jre/bin:/opt/bitnami/nami/bin:/opt/bitnami/apache/bin:/opt/bitnami/apache2/bin:/opt/bitnami/common/bin:/opt/bitnami/git/bin:/opt/bitnami/gonit/bin:/opt/bitnami/java/bin:/opt/bitnami/java/jre/bin:/opt/bitnami/nami/bin:/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games'
	NVM_BIN='/home/bitnami/.nvm/versions/node/v12.18.4/bin'
    } **/

    stages {

       stage('NPM Setup') {
	  agent { docker { image  'ghcr.io/ionic-team/ionic-cli:6.11.10' } }
          steps {
             sh 'whoami'
	     sh 'id'
             sh 'ionic --version'
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
