// This is an example of a declarative pipeline in Jenkins
pipeline { // Specifies we want to create a pipeline

    agent any  // Here we declare where we want our pipeline to be executed
               // i.e. in a cluster of Jenkins slaves and master we specify which node the job will be executed
    parameters { // We can create parameters for our Jenkins projects in this file
        choice(name: 'Branch', choices: ['main', 'dev'])
    }
    stages {  // The stages is where the actual workflow is specified

        stage("build") { // A task to be executed in a Jenkins pipeline workflow
            steps {  // Steps to execute a task in the workflow
                echo 'building the app...'
            }
        }
        stage("test") {
            when { // A conditional statement we impose on a strage
                expression { // The expression our conditional evaluates
                    BRANCH_NAME == 'dev' || BRANCH_NAME == 'main'
                }
            } // The step will only execute if the conditional is met
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
    post { // Execute some logic after all stages have been executed
    always { // conditions = [always,success,failure]
        //
    }
    }
}