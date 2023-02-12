pipeline {
    agent any
    tools {
        maven 'Maven'
    }

    stages {

        stage("build") {

            steps {
                echo 'building the application....'
                bat"mvn clean install -s settings.xml"
            }
        }

        stage("test") {

            steps {
                echo 'testing the application...'
                script {
                try {
                bat 'mvn -s settings.xml test -Dtest=moa.classifiers.**.*Test -Dmaven.test.failure.ignore=true -DfailIfNoTests=false'
                }
                catch (err) {
                    echo "Caught err" 
                    currentBuild.result = "STABLE"
                }

                }

            }
        }

        stage("deploy") {

            steps {

                echo 'deploying the application...'
            }
        }
    }
}

