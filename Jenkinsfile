pipeline {
    agent any
    parameters {
        string(name: 'USER', defaultValue: 'Srikar', description: 'Username')
    }
    environment {
        REGION = "us-east1"
    }
    
    stages {
        stage('STAGE1') {
            when {
                
                             environment name: "REGION", value: "us-east1"
            }
            steps {
                echo "This is stage 1"
                echo "${params.USER}"
                echo "${REGION}"
                sh """
                    echo "${params.USER}"
                    echo "${REGION}"
                    sleep 5
                    echo "This is a linux command"
                """
            }
        }
        stage('STAGE2') {
            steps {
                catchError(buildResult: "UNSTABLE", stageResult: "FAILURE"){
                    
                sh """
                    exit 1
                """
                }
            }
        }
    }
}
