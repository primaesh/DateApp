pipeline {
    agent any
    tools {
        jdk 'Java17'
        maven 'Maven3'
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/primaesh/DateApp.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                script {
                    def warFile = 'target/DateApp-1.0-SNAPSHOT.war'
                    def tomcatURL = 'http://<13.126.149.70>:8080/manager/text'
                    def tomcatUser = '<admin>'
                    def tomcatPass = '<admin>'
                    sh """
                        curl -u ${admin}:${admin} -T ${webapps} ${http://13.126.149.70:8080/}/deploy?path=/DateApp
                    """
                }
            }
        }
    }
}
