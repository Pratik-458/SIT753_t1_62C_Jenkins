pipeline {
    agent any
    environment {
        DIRECTORY_PATH = "https://github.com/Pratik-458/SIT753_t1_62C_Jenkins.git"
        TESTING_ENVIRONMENT = "Testing Environment"
        PRODUCTION_ENVIRONMENT = "pratikpawar"
    }
    stages {

        stage("Build") {
            steps {
                echo "fetch the source code from the directory path specified by the environment variable"
                echo "compile the code and generate any necessary artifacts"
                echo "Maven is a build automation tool used primarily for Java projects. Maven can also be used to build and manage projects written in C#, Ruby, Scala, and other languages "
            }
            post{
                always{
                    emailext attachLog: true,
                    mail to: "pratikmel162@gmail.com",
                    subject: "Build stage email",
                    body: "Build log attached"
                }
            }
        }
        stage("Test") {
            steps {
                echo "Running unit tests for the application..."
                echo "Running integration tests for the application..."
            }
        }
        stage("Code Quality Check") {
            steps {
                echo "check the quality of the code for the application..."
            }
        }
        stage("Deploy") {
            steps {
                echo "deploy the application to a testing environment specified by the environment variable"
            }
        }
        stage("Approval") {
            steps {
                echo "Approval stage..."
                sleep(time: 10, unit: 'SECONDS')
            }
        }
        stage("Deploy to Production") {
            steps {
                echo "Deploying to Production environment ${PRODUCTION_ENVIRONMENT}"
            }
        }
        

    }
}