pipeline {
    agent any
    tools {
        maven 'Maven'
    }

    stages {

        stage("build") {

            steps {
                echo 'building the application...'
                // bat"mvn clean install -s settings.xml"
            }
        }

        stage("test") {

            steps {
                echo 'testing the application...'
                bat "mvn test '-Dtest=moa.classifiers.**.*Test'"
            }
        }

        stage("deploy") {

            steps {
                echo 'deploying the application...'
            }
        }
    }
}

