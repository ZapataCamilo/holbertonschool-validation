# Awesome Website

Project for DevOps on Holberton School

## Prerequisites
GoHugo on extended version - v0.84 or above make - v3.81 or above

## Lifecycle
build:	 Generate the website from the markdown and configuration files in the directory dist/ and compile the source code of the application to a binary named awesome-api (the name awesome-api comes from the command
clean:	 Cleanup the content of the directory dist/, the binary awesome-api and the log file awesome-api.log
post:	 Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME.
run:     Run the application in background by executing the binary awesome-api, and write logs into a file named awesome-api.log
stop:    Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application.
test:    You want to test it to ensure that it behaves as expected. With the application started, you may want to use the command line curl
lint:    ## Static linting on go files using golangci-lint
unit-tests:      it should execute (successfully) the Golang unit tests:
integration-tests:       implemented and should execute (successfully) the Golang integration tests
check:	 Analysis of the links
validate:	 should validate the file ./dist/index.html by using the command line Holberton’s W3C Validator
help:	 Show this help message
