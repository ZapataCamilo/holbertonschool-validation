build:	## Generate the website from the markdown and configuration files in the directory dist/ and compile the source code of the application to a binary named awesome-api (the name awesome-api comes from the command
	make lint
	go build
	hugo

clean:	## Cleanup the content of the directory dist/, the binary awesome-api and the log file awesome-api.log
	rm -rf ./dist
	-make stop
	-rm ./awesome-api ./awesome-api.log ./coverage-units.out 

post:	## Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME.
	hugo new posts/${POST_NAME}.md
	sed -i 's/^title:.*/title: ${POST_TITLE}/g' ./content/posts/${POST_NAME}.md

run:    ## Run the application in background by executing the binary awesome-api, and write logs into a file named awesome-api.log
	./awesome-api >./awesome-api.log 2>&1 &

stop:   ## Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application.
	kill "$(shell pgrep awesome-api)"

test:   ## You want to test it to ensure that it behaves as expected. With the application started, you may want to use the command line curl
	make unit-tests
	make integration-tests

lint:   ## ## Static linting on go files using golangci-lint
	@golangci-lint run

unit-tests:     ## it should execute (successfully) the Golang unit tests:
	@go test -v -short -coverprofile=coverage-units.out     

integration-tests:      ## implemented and should execute (successfully) the Golang integration tests
	@go test -v -coverprofile=coverage-integrations.out

check:	## Analysis of the links
	markdown-link-check ./content/posts/*
	markdownlint ./content/posts/*

validate:	## should validate the file ./dist/index.html by using the command line Holberton’s W3C Validator
	-./w3c_validator.py ./dist/index.html

help:	## Show this help message
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'