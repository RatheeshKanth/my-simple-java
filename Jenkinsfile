node
{
    stage('clonning from GIT'){
	git 'https://github.com/RatheeshKanth/my-simple-java.git'
     }

stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarServer'
      withSonarQubeEnv('SonarServer') {
      sh """var/jenkins_home/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarServer/bin/sonar-scanner \
       -D sonar.login=admin \
      -D sonar.password=admin123 \
      -D sonar.projectBaseDir=var/jenkins_home/workspace/my-java-app/java/ \
        -D sonar.projectKey=my-app \
        -D sonar.sourceEncoding=UTF-8 \
        -D sonar.language=java \
        -D sonar.sources=my-simple-java/java/ \
        -D sonar.tests=my-simple-java/test/ \
        -D sonar.host.url=http://54.175.78.57:9000/"""
        }
}
}

