pipeline {

    agent any

    /* environment {
        PATH='/home/bitnami/.nvm/versions/node/v12.18.4/bin:/opt/bitnami/apache/bin:/opt/bitnami/apache2/bin:/opt/bitnami/common/bin:/opt/bitnami/git/bin:/opt/bitnami/gonit/bin:/opt/bitnami/java/bin:/opt/bitnami/java/jre/bin:/opt/bitnami/nami/bin:/opt/bitnami/apache/bin:/opt/bitnami/apache2/bin:/opt/bitnami/common/bin:/opt/bitnami/git/bin:/opt/bitnami/gonit/bin:/opt/bitnami/java/bin:/opt/bitnami/java/jre/bin:/opt/bitnami/nami/bin:/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games'
	NVM_BIN='/home/bitnami/.nvm/versions/node/v12.18.4/bin'
    } **/
      tools {
    // a bit ugly because there is no `@Symbol` annotation for the DockerTool
    // see the discussion about this in PR 77 and PR 52: 
    // https://github.com/jenkinsci/docker-commons-plugin/pull/77#discussion_r280910822
    // https://github.com/jenkinsci/docker-commons-plugin/pull/52
    'org.jenkinsci.plugins.docker.commons.tools.DockerTool' '18.09'
  }

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
