pipeline {
    agent any
    options {
        skipDefaultCheckout()
    }
    stages {
        stage("Git step on main branch") {
            steps {
                // JENKINS-64320 reports that help for git step incorrectly says that
                // branch parameter will be the default branch of the remote repo.
                // That is incorrect. It will be the branch named 'master', no matter
                // the default branch of the remote repository.
                ws('JENKINS-64320-main-branch') {
                    // the default branch is not used unless it is named 'master'.
                    git branch: 'main', url: 'https://github.com/MarkEWaite/JENKINS-64314'
                }
            }
        }
        stage("Git step no branch specified") {
            steps {
                ws('JENKINS-26197-no-branch') {
                    // Works because repo JENKINS-26197 default branch is 'master'
                    git url: 'https://github.com/MarkEWaite/JENKINS-26197'
                }
            }
        }
        stage("Git step default branch") {
            steps {
                ws('JENKINS-64320-default-branch') {
                    catchError {
                        // Fails because repo JENKINS-64314 default branch is 'main'
                        git url: 'https://github.com/MarkEWaite/JENKINS-64314'
                    }
                }
            }
        }
    }
}
