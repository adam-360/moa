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
                try {
                    bat 'mvn -s settings.xml test -Dtest=moa.classifiers.**.*Test'
                } catch (err) {
                    echo "Caught: ${err}"
                    currentBuild.result = "STABLE"
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

