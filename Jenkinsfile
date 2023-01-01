node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'DefaultMaven';
    withSonarQubeEnv() {
      bat "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=test-zk-maven-pipeline"
    }
  }
}