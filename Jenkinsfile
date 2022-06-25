node
{
    stage('clonning from GIT'){
git branch: 'main', credentialsId: 'GIT_REPO', url: 'https://github.com/devopshint/sonarqu...
     }

stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarServer'
      withSonarQubeEnv('SonarQube') {
      sh """/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarQube/bin/sonar-scanner \
     -D sonar.projectVersion=1.0-SNAPSHOT \
       -D sonar.login=admin \
      -D sonar.password=admin123 \
      -D sonar.projectBaseDir=/var/lib/jenkins/workspace/jenkins-sonar/ \
        -D sonar.projectKey=my-app \
        -D sonar.sourceEncoding=UTF-8 \
        -D sonar.language=java \
        -D sonar.sources=my-simple-java/java \
        -D sonar.tests=my-simple-java/test \
        -D sonar.host.url=http://100.26.192.227:9000/"""
        }
}
}

