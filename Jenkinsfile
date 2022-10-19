pipeline {
    agent {
        docker {
            image 'proninmo/appbuilder'
        }
    }

    stages {
        stage ('Git Clone App file') {
            steps {
                git 'https://github.com/proninmo/boxfuse-test.git'
            }
        }
        stage ('Buld war') {
            steps {
                sh 'cd boxfuse-*'
                sh 'mvn package'
            }           
        }
        stage ('Make imagefile with app') {
            steps {

            }
        }
        stage ('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'aec0ea23-59e5-44e7-85b9-0dc3f3cf97b4', path: '', url: 'http://84.201.179.14:8080')], contextPath: 'mywebapp2', war: '**/*.war'
            }
        }
    }
}