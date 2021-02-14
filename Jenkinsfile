node {
    stage('git clone') {
        git credentialsId: 'jenkins', url: 'git@gitlab.com:bileli/projet_j2ee.git'
    }

    stage('Build') {
        sh 'mvn clean install package'
    }
    
    stage('Deploy') {
        deploy adapters: [tomcat8(credentialsId: 'tomcat', path: '', url: 'http://51.83.72.127:8080/')], contextPath: null, war: '**/*.war'
    }
    
}
