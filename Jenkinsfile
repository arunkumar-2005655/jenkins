node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv(sonarqube) {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=sonardemo -Dsonar.projectName='sonardemo'"
    }
  }
}
