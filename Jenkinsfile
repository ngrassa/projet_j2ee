node {
    stage('git clone') {
        git branch: 'sonar', credentialsId: 'jenkins', url: 'git@gitlab.com:bileli/projet_j2ee.git'
    }
    
    stage('SonarQube analysis') {
        withSonarQubeEnv {
            sh 'mvn clean package sonar:sonar'
        }
    }
    
    stage('Quality Gate') {
        waitForQualityGate abortPipeline: true
      
    }
    
   
}
