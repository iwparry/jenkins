// This is an example of a declarative pipeline in Jenkins
def gv
pipeline { // Specifies we want to create a pipeline

    agent any  // Here we declare where we want our pipeline to be executed
               // i.e. in a cluster of Jenkins slaves and master we specify which node the job will be executed

    parameters {
        choice(name:'Branch', choices: ['main', 'dev'])
    }
    environment {
        BRANCH_NAME = choice('Branch')
    }
    stages {  // The stages is where the actual workflow is specified

        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build") { // A task to be executed in a Jenkins pipeline workflow
            steps {  // Steps to execute a task in the workflow
                script {
                  gv.buildApp()
                }
            }
        }
        stage("test") {
            steps {
                script {
                    gv.testApp()
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    gv.deployApp()
                }
            }
        }
    }
}