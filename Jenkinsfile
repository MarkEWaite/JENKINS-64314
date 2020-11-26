pipeline {
    agent any
    options {
        skipDefaultCheckout()
    }
    stages {
        stage("Git step") {
            steps {
                // JENKINS-64320 reports that help for git step incorrectly says that
                // the default branch is not used unless it is named 'master'.
                git branch: 'main', url: 'https://github.com/MarkEWaite/JENKINS-64314'
            }
        }
    }
}
