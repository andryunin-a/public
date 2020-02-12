#!groovy
// Check properties
properties([disableConcurrentBuilds()])

pipeline {
    agent {        
        dockerfile true
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
        stage("Hello2") {
            steps {
                echo 'Hello World 2'
            }
        }      
    }
}
