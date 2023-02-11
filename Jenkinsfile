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
                configFileProvider([configFile(fileId: 'db8e2cd0-8965-4726-b461-566bd803175a', variable: 'MAVEN_SETTINGS_XML')]) {
                    bat 'mvn -s $MAVEN_SETTINGS_XML test -Dtest=moa.classifiers.**.*Test'
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

