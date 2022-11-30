pipeline {

    tools {
        dockerTool "docke-jenkins"
    }

    agent {
        label 'docker'
    }

    stages {

        stage('Docker node test') {
              agent {
                docker {
                  label 'docker'
                  image 'node:7-alpine'
                  args '--name node-js' // list any args
                }
              }
              steps {
                // Steps run in node:7-alpine docker container on docker agent
                sh 'node --version'
              }
            }

        stage('build') {
            steps {
                sh 'echo "Hello World"'
            }
        }
        stage('test') {
            steps {
                sh 'echo "Fail!"; exit 1'
            }
        }
    }
}