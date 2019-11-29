#!/usr/bin/env groovy

/*
 * This Jenkinsfile is intended to run on https://ci.jenkins.io and may fail anywhere else.
 * It makes assumptions about plugins being installed, labels mapping to nodes that can build what is needed, etc.
 */

// noinspection GroovyAssignabilityCheck

pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('aws-access-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('aws-secret-access-key')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                script {
                    def outputFilePath = "Jenkinsfile"
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'printenv'
                echo '${outputFilePath}'
//            sh 'aws s3 cp ${outputFilePath} s3://rp-bet-prompts-dev-tetiana/social-tournaments/'
            }
        }
    }

}
