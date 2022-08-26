node
{
    stage('clonning from GIT'){
	git 'https://github.com/RatheeshKanth/my-simple-java.git'
     }

    stage('SonarQube Analysis') {
        def scannerHome = tool 'SonarServer' ;
         withSonarQubeEnv('SonarServer') {
         sh "${scannerHome}/bin/sonar-scanner \
          -D sonar.login=admin \
          -D sonar.password=admin123 \
          -D sonar.projectKey=my-app \
          -D sonar.sources=src/main/ \
          -D sonar.test=src/test/ \
          -D sonar.exclusions=vendor/**,resources/**,**/*.java \
          -D sonar.host.url=http://54.175.78.57:9000/"
        }
}
}

