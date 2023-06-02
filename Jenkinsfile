// This is an example of a declarative pipeline in Jenkins
pipeline { // Specifies we want to create a pipeline

    agent any  // Here we declare where we want our pipeline to be executed
               // i.e. in a cluster of Jenkins slaves and master we specify which node the job will be executed

    stages {  // The stages is where the actual workflow is specified

        stage("build") { // A task to be executed in a Jenkins pipeline workflow
            steps {  // Steps to execute a task in the workflow
                echo 'building the app...'
            }
        }
        stage("test") {
            steps {
                echo 'testing the app...'
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the app...'
            }
        }
    }
}