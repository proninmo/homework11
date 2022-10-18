pipeline {
    agent any
    tools {
        maven "m3"
    }

    stages {
        stage ('Git Clone') {
            steps {
                git 'https://github.com/proninmo/boxfuse-test.git'
            }
        }
        stage ('Buld') {
            steps {
                sh 'mvn package'
            }
        }
        stage ('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'aec0ea23-59e5-44e7-85b9-0dc3f3cf97b4', path: '', url: 'http://84.201.179.14:8080')], contextPath: 'mywebapp2', war: '**/*.war'
            }
        }
    }
}