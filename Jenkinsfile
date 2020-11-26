pipeline {
    agent any
    options {
        skipDefaultCheckout()
    }
    stages {
        stage("Git step") {
            steps {
                // JENKINS-64320 reports that help for git step incorrectly says that
                ws('JENKINS-64320') {
                    // the default branch is not used unless it is named 'master'.
                    git branch: 'main', url: 'https://github.com/MarkEWaite/JENKINS-64314'
                }

                // Fails because repo JENKINS-64314 default branch is 'main'
                // git url: 'https://github.com/MarkEWaite/JENKINS-64314'

                ws('JENKINS-26197') {
                    // Works because repo JENKINS-26197 default branch is 'master'
                    git url: 'https://github.com/MarkEWaite/JENKINS-26197'
                }
            }
        }
    }
}
