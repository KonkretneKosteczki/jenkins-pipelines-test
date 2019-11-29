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
        AWS_DEFAULT_REGION = "eu-central-1"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                script {
                    outputFilePath = "Jenkinsfile"
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                echo '${outputFilePath}'
                sh 'aws s3 cp Jenkinsfile s3://rp-bet-prompts-dev-tetiana/social-tournaments/'
            }
        }
    }

}
