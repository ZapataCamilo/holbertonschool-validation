## golang project

# Prerequisites
golang latest version
make latest version

# Lifecycle
build:	 compile the source code of the application to a binary named awesome-api (the name awesome-api comes from the command
run:	 Run the application in background by executing the binary awesome-api, and write logs into a file named awesome-api.log
stop:	 Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application.
clean:	 Stop the application. Delete the binary awesome-api and the log file awesome-api.log
test:	 You want to test it to ensure that it behaves as expected. With the application started, you may want to use the command line curl
lint:	 ## Static linting on go files using golangci-lint
unit-tests:	 it should execute (successfully) the Golang unit tests:
integration-tests:	 implemented and should execute (successfully) the Golang integration tests
help:	 Show help massage
