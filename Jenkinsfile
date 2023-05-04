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
                echo "Maven is a build automation tool."
            }
            
        }
        stage("Test") {
            steps {
                echo "Using JUnit for unit testing..."
                echo "Using Selenium for integration testing..."
            }
            post{
                always{
                    emailext(attachLog: true,
                    to: "pratikmel162@gmail.com",
                    subject: "Test on lower environment email",
                    body: "testing logs attached ${currentBuild.result}: ${BUILD_URL}")
                }
            }
        }
        stage("Code Analysis") {
            steps {
                echo "Using SonarQube to check the quality of the code..."
            }
        }
        stage("Security Scan") {
            steps {
                echo "Using OWASP ZAP to identify any vulnerabilitie..."
            }
            post{
                always{
                    emailext(attachLog: true,
                    to: "pratikmel162@gmail.com",
                    subject: "Security Scan stage email",
                    body: "Security scan logs attached ${currentBuild.result}: ${BUILD_URL}")
                }
            }
        }
        stage("Deploy to staging") {
            steps {
                echo "Using AWS CodeDeploy to deploy the application to a staging environment"
            }
        }
        stage("Test on staging") {
            steps {
                echo "Using SonarQube for running integration tests on staging environment..."
            }
            post{
                always{
                    emailext(attachLog: true,
                    to: "pratikmel162@gmail.com",
                    subject: "Test on Staging environment email",
                    body: "Staging Test logs attached ${currentBuild.result}: ${BUILD_URL}")
                }
            }
        }
        stage("Deploy to Production") {
            steps {
                echo "Using AWS CodeDeploy to deploy the application to a production server. ${PRODUCTION_ENVIRONMENT}"
            }
        }
        

    }
}