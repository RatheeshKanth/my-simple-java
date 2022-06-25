node
{
    stage('clonning from GIT'){
	git 'https://github.com/RatheeshKanth/my-simple-java.git'
     }

stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarServer'
      withSonarQubeEnv('SonarServer') {
      sh /var/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarServer/bin/sonar-scanner \
    // -D sonar.projectVersion=1.0-SNAPSHOT \
       -D sonar.login=admin \
      -D sonar.password=admin123 \
      -D sonar.projectBaseDir=/var/jenkins/workspace/my-java-app/java \
        -D sonar.projectKey=my-app \
        -D sonar.sourceEncoding=UTF-8 \
        -D sonar.language=java \
        -D sonar.sources=my-simple-java/java \
        -D sonar.tests=my-simple-java/test \
        -D sonar.host.url=http://100.26.192.227:9000/"""
        }
}
}

