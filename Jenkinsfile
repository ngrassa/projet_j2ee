node {
    stage('SonarQube analysis') {
        withSonarQubeEnv {
            sh 'mvn clean package sonar:sonar'
        }
    }
    
    stage('Quality Gate') {
        waitForQualityGate abortPipeline: true
      
    }
    stage('Build') {
        sh 'mvn clean install package'
    }
