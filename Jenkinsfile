pipeline {
    agent any

    stages {
        stage('Fetch Code') {
            steps {
                git 'https://github.com/Kesavkrish01/Maven-Build.git'
            }
        }
        stage('Maven-Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Deploy Application') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '9603c5bd-6835-40d8-a6ab-59751eb662c2', path: '', url: 'http://192.168.44.130:9090')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
