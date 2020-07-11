pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                sh 'mvn clean package'
            }
        }
        stage("Deploy") {
            steps {
                deploy adapters: [tomcat8(credentialsId: '60d0d2ee-b2f4-4929-9fee-d9a5bdb49b37', 
                path: '', 
                url: 'http://ec2-35-181-1-9.eu-west-3.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
