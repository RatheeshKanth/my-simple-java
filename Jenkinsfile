pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
		git 'https://github.com/RatheeshKanth/my-simple-java.git'
               		 echo 'Cloning...'
            }
        }
       stage('SonarQube analysis') {
    		def scannerHome = tool 'sonarqube';
   		 withSonarQubeEnv('sonarqube') {
      		sh "${scannerHome}/bin/sonar-scanner \
      		-D sonar.login=admin \
      		-D sonar.password=admin \
      		-D sonar.projectKey=sonarqube \
      		-D sonar.exclusions=vendor/**,resources/**,**/*.java \
      		-D sonar.host.url=http://174.129.179.126:9000/"
    }
  }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
