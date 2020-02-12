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
        stage("Hello2") {
            steps {
                echo 'Hello World 2'
            }
        }
        
        stage('Build') {
            docker.image('maven:3.3.3-jdk-8').inside {
  git 'https://github.com/andryunin-dev/jenkins.git'
  sh 'mvn -B clean install'
}
      
      
   }
    }
}
