#!groovy
// Check properties
properties([disableConcurrentBuilds()])

pipeline {
    agent {
        label 'master'
    }
    triggers { pollSCM('* * * * *') }
    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
    }
    stages {
        stage("Hello") {
            steps {
                echo 'Hello World'
            }
        }
    }
}
