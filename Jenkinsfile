pipeline {
    agent any
    options {
        skipDefaultCheckout()
    }
    stages {
        stage("Git step") {
            steps {
                git branch: 'main', url: 'https://github.com/MarkEWaite/JENKINS-64314'
            }
        }
    }
}
