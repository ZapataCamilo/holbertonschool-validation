build:	## compile the source code of the application to a binary named awesome-api (the name awesome-api comes from the command
	make lint
	go build

run:	## Run the application in background by executing the binary awesome-api, and write logs into a file named awesome-api.log
	./awesome-api >./awesome-api.log 2>&1 &

stop:	## Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application.
	kill "$(shell pgrep awesome-api)"

clean:	## Stop the application. Delete the binary awesome-api and the log file awesome-api.log
	-make stop
	-rm ./awesome-api ./awesome-api.log

test:	## You want to test it to ensure that it behaves as expected. With the application started, you may want to use the command line curl
	-curl http://localhost:9999
	curl http://localhost:9999/health

lint:	## ## Static linting on go files using golangci-lint
	@golangci-lint run

help:	## Show help massage
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'