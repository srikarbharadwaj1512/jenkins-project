pipeline {
    agent any
    parmeters {
        USER: "Srikar"
    }
    environment {
        REGION: "us-east1"
    }
    
    stages {
        stage('STAGE1') {
            // agent slave1
            steps {
               echo "This is the stage 1"
               echo "${params.USER}"
               echo "${REGION}"
               sh '''
                    echo "${params.USER}"
                    echo "${REGION}"
                    sleep 5
                    echo "This is a linux command"
                '''
            }
        }
        stage('Build') {
            steps {
                echo "Building Java code"
                sh '''
                    #!/bin/bash
                    sleep 5
                '''
            }
        }
    }
}
